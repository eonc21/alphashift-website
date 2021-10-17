<template>
     <div class="link-list" :key="navLink.name" v-for="navLink in navLinks" id='navLink'>
         <Link :navLink="navLink" />
    </div>
  
</template>

<script>
import Link from './Link.vue'

export default {
    name: 'LinkList',

    props: {
        navLinks: Array,
    },

    components: {
        Link,

    }



}
</script>

<style>
.link-list {
    width: 25%;
    line-height: 35px;
}

</style>