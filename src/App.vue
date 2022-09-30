<template>
  <div>
    <ul>
      <li v-for="(i,index) in arr" :key="i.id">
        <p>id:{{index}}</p>
        <p>name:{{i.name}}</p>
        <p>hobby:{{i.hobby}}</p>
      </li>


    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      arr: [
        {
          id: 1,
          name: 'ajck',
          hobby: 'run'

        },
        {
          id: 1,
          name: 'ajck',
          hobby: 'run'

        },
        {
          id: 1,
          name: 'ajck',
          hobby: 'run'

        },
      ]
    }
  }
}
</script>

<style>

</style>