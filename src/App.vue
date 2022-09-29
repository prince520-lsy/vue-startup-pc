<template>
  <div>
  <h1>案例：折叠面板</h1>
  <h4>芙蓉楼送辛渐</h4>
  <p v-show="show">寒雨连江夜入屋，</p>
  <p v-show="show">平明送客蜀山股。</p>
  <p v-show="show">洛阳亲友如想问，</p>
  <p v-show="show">一片冰心在玉壶。</p>
  <button @click="show=!show">{{show==false?'显示':'收起'}}</button>
  </div>
</template>
<script>
export default {
  data() {
      return {
        show: true,
        
      }
  },

methods: {
  toggle() {

  }
  }
}
</script>
<style>

</style>