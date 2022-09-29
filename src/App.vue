<template>
  <div>
      <button @click="nav">log(hello)</button>
      <button @click="count++">+</button>
      <span>{{count}}</span>
      <button @click="count--">-</button>
      <button @click="add(10)">加10</button>
      <button @click="add(100)">加100</button>
      <a href="https://www.baidu.com" @click='fn'>百度</a><br>
      <a href="https://www.baidu.com" @click.prevent="nav">百度</a>
  </div>
</template>

<script>

export default {
  data() {
    return {
     count:0
    }
  },
  methods: {

    fn(e) {
      e.preventDefault();
    },
    nav() {
      console.log('hello world');
    },
    add(num) {
      this.count += num;
    }
  }
}
</script>

<style>

</style>
