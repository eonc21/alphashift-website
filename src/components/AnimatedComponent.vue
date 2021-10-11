<template>
  <div ref="target">
    <transition :name="animationType">
      <div v-appear="animate" class="animated-component">
        <slot />
      </div>
    </transition>
  </div>
</template>
<script lang="js">
import { onMounted, ref } from 'vue';
export default {
  name: 'AnimatedComponent',
  props: {
    animationType: {
      type: String,
      required: false,
      default: 'fade'
    }
  },
  setup() {
    const target = ref();
    const animate = ref(false);
    const observer = new IntersectionObserver(
      ([entry]) => {
        animate.value = entry.isIntersecting;
      },
      {
        threshold: 0.4
      }
    );
    onMounted(() => {
      observer.observe(target.value);
    });
    return {
      animate,
      target
    };
  }
};
</script>

<style scoped>

#animated-component {
    display: flex;
    justify-content: space-evenly;
    align-content: center;
    align-self: center;
    /* border: 1px solid pink; */
}
.animated-component.fade-enter-from,
.animated-component.zoom-enter-from {
  transition: none;
}
/* Fade animation */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 500ms ease-in-out;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
/* Zoom animation */
.zoom-enter-active,
.zoom-leave-active {
  transition: transform 450ms ease;
}
.zoom-enter-from,
.zoom-leave-to {
  transform: scale(0.8);
}
</style>
