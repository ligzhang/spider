<template>
  <div id="app">
  <h1 v-html='title'></h1>
  <input v-model= 'newItem' v-on:keyup.enter='addNew'>
  <ul >
    <li v-for = 'item in items' v-bind:class='{finished:item.isFinished}' >
      {{ item.label }} <button v-on:click='toggle(item)' >完成</button> <button v-on:click='del(item)' >删除</button>
    </li>
  </ul>
  <Hello></Hello>
  <Version></Version>
  <div class="" id="main" :style="{width:200+'px',height:200+'px'}" >

  </div>
  <Table>
  </Table>
  </div>
</template>

<script>
import Store from './store'
import Hello from './components/Hello'
import Version from './components/Version'
import Table from './components/table'
var echarts = require('echarts')
console.log(echarts, '***')

export default {
  data: function () {
    return {
      title: 'this is a todo list',
      newItem: ' ',
      items: Store.fetch()
    }
  },
  watch: {
    items: {
      handler: function (item) {
        Store.save(item)
      },
      deep: true
    }
  },
  mounted () {
    var myChart = echarts.init(document.getElementById('main'))
    myChart.setOption({
      title: { text: 'ECharts 入门示例' },
      tooltip: {},
      xAxis: {
        data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
      },
      yAxis: {},
      series: [{
        name: '销量',
        type: 'bar',
        data: [5, 20, 36, 10, 10, 20]
      }]
    })
  },
  methods: {
    toggle: function (item) {
      item.isFinished = !item.isFinished
      console.log('list', this.items)
    },
    del: function (item) {
      var index = this.items.indexOf(item)
      console.log(index, 'index')
      this.items.splice(index, 1)
    },
    addNew: function () {
      // this.items = []
      this.items.push({
        label: this.newItem,
        isFinished: false
      })
      this.newItem = ' '
    }
  },
  components: {Hello, Version, Table}
}
</script>

<style>
  #app{
      font-size:30px;
      text-align:center;
  }
  .finished{
      text-decoration: line-through;
  }
  .hidden {
      display:none;
  }
  #main {
      display: flex;
      justify-content: center;
  }
</style>
