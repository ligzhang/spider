<template lang="html">
    <div class="">
        <div class='item'>
            <div>姓名</div>
            <div>年龄</div>
        </div>
        <div v-for='item in employ' class='item'>
            <div v-for='newItem in item'>{{newItem}}</div>

        </div>
    </div>

</template>

<script>
export default {
  data () {
    return {
      employ: [{name: 'zlg', age: 20},
            {name: 'lll', age: 30}]
    }
  }
}
</script>

<style lang="css">
    .item {
        display: flex;
        justify-content:  flex-start;
    }
</style>
