<template>
  <ul>
    <li v-for="(user) in users" :key="user.id">
      {{user.id}}:{{user.name}}
    </li>
  </ul>
</template>

<script>
import axios from 'axios';
export default {
  name: 'app',
  data(){
    return {
      users:[]
    }
  },
  mounted(){
    axios.get('http://127.79.205.221:3000/api/users').then(response=>{
      this.users = response.data;
    });
  }
}
</script>

<style>
</style>
