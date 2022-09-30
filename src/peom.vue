<template>
    <div>
    <h1>案例：折叠面板</h1>
    <p>username:<input type="text" v-model="username">admin</p>
    <p>password:<input type="text" v-model="password">123</p>
    <button @click="login">登录</button>
    </div>
</template>
<script>
export default {
    data() {
        return {
            username: '',
            password: '',
            
        }
    },

methods: {
    login() {
            console.log(this.username,this.password);
        }
    }
}
</script>
<style>

</style>