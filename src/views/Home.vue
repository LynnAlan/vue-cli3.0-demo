<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <MeetingRoom></MeetingRoom>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import { getUserInfo } from '@/api/test'
export default {
  name: 'home',
  components: {
    HelloWorld
  },
  created () {
    console.log(process.env.BASE_URL)
    this.getTest();
  },
  methods:{
    async getTest(){
      let res = await getUserInfo();
      console.log(res)
    }
  }
}
</script>
