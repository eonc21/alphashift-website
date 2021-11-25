<template>
  <div id="member-list" :key="member.name" v-for="member in members">
    <Member :member="member" />
      
  </div>
</template>

<script>

import Member from "./Member.vue"
export default {
    name: "MemberList",

    components: {
        Member,
    },

    props: {
        members: Array,
    }

}
</script>

<style>
#member-list {
  display: flex;
  flex-direction: row;
  justify-content: center;
  flex-wrap: wrap;
  width: 30%;
  margin: auto;
}

@media (max-width: 600px){
  #member-list {
    width: 100%;
    /* height: 200px; */
    justify-content: center;
    /* overflow: hidden; */
  }
}

</style>