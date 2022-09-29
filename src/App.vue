<template>
  <div id="app">
      <div>Jack今年{{age1}}岁  {{age1>=18?'成年':'未成年'}}</div>
      <div>Jane今年{{age2}}岁  {{age2>=18?'成年':'未成年'}}</div>
      <div>{{num1}}+{{num2}}={{num1+num2}}</div>
      <ul>
        <li>Name:{{student.name}}</li>
        <li>Age:{{student.age>=18?'成年':'未成年'}}</li>
        <li>Sex:{{student.gender}}</li>
      </ul>
      <h1>今年是{{getYear()}}</h1>
      <a :href="url">百度</a>
      <img :src="urlLogo" alt="">
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  data() {
    return {
      age1: 10,
      age2: 20,
      num1: 100,
      num2: 200,
      student: {
        name: 'jack',
        age: '22',
        gender:'boy'
      },
      url:'https://www.baidu.com/',
      urlLogo: 'https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png',
      ok: true,
      notok: false,
      user: 'Jack',
      password:'123456'
    }
  },
  methods: {
    getYear() {

            return new Date().getFullYear();
        }
    }
  
}
</script>

<style>

</style>
