<template>
  <div>
  <h1>注册</h1>
  <p>username:<input type="text" v-model.trim="username"></p>
  <p>password:<input type="password" v-model.trim="password"></p>
  <p>age: <input type="text" v-model.number="age"></p>
  <button @click="login">注册</button>

  </div>
</template>
<script>
export default {
  data() {
      return {
          username: 'admin',
          password: '123',
          age:'12',
      }
  },

methods: {
  login() {
          console.log(this.username,this.password,this.age);
      }
  }
}
</script>
<style>

</style>