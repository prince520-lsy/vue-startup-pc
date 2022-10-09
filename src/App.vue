<template>
  <div class="container">
    <div class="row">
      <div class="col-12 pt-3">
        <table class="table table-bordered">
          <thead>
            <tr>
              <th scope="col">编号</th>
              <th scope="col">资产名称</th>
              <th scope="col">价格</th>
              <th scope="col">创建时间</th>
              <th scope="col">操作</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(item, index) in list" :key="item.id">
              <th scope="row">{{item.id}}</th>
              <td>{{item.subject}}</td>
              <td :class="{'not-pass':item.score<100}">{{item.score}}</td>
              <td>{{formatDate(item.time)}}</td>
              <td>
                <button type="button" class="btn btn-link" @click="del(index)">删除</button>
              </td>
            </tr>

            <tr class="bg-light">
              <th scope="row">统计</th>
              <td colspan="2">总价：{{totol}}</td>
              <td colspan="2">均价：{{aver?aver:'0'}}</td>
            </tr>
          </tbody>
          <tfoot style="display: none">
            <tr>
              <td class="text-center" colspan="5">暂无数据</td>
            </tr>
          </tfoot>
        </table>
      </div>
    </div>

    <form class="row align-items-center" @submit.prevent="">
      <div class="col-3">
        <input type="text" class="form-control" placeholder="资产名称" v-model.trim="subject" />
      </div>

      <div class="col-3">
        <input type="text" class="form-control" placeholder="价格" v-model.number="score" />
      </div>

      <div class="col-3">
        <button type="submit" class="btn btn-primary" @click="add">添加资产</button>
      </div>
    </form>
  </div>
</template>

<script>
import moment from 'moment'
export default {
  name: "App",
  methods: {
    del(index) {
      this.list.splice(index, 1)
    },
    add() {
      let last = this.list[this.list.length - 1]
      this.list.push({
        id: last ? last.id + 1 : 100,
        subject: this.subject,
        score: this.score,
        time: new Date()

      })
      this.subject = '',
        this.score = '';
    },
    formatDate(time) {
      return moment(time).format("YYYY-MM-DD  HH:mm:ss");
    }
  },
  watch: {
    list(newvalue, oldvalue) {
      localStorage.setItem('list', JSON.stringify(newvalue))
    }
  },
  created() {
    this.list = JSON.parse(localStorage.getItem('list'))

  },
  data() {
    return {
      list: [],
      subject: '',
      score: ''
    };
  },
  computed: {
    totol() {
      let sum = 0
      this.list.forEach((item) => {
        sum += item.score

      })
      return sum
    },
    aver() {
      return this.totol / this.list.length
    }
  }
};
</script>
<style scoped>
.not-pass {
  color: red;
}
</style>
