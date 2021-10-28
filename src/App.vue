<template>
  <div>
    {{this.info}}
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'App',
  data: function() {
    return {
      info:{}
    };
  },
  components: {

  },
  methods:{
    getInfo(){
      axios.get("/api/notice/getNotices").then(resp => {
        this.info = resp.data;
        console.log(this.info)
      })
    }
  },
  created() {
    this.getInfo()
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
