<template>
  <div>
    <ul class="navlist">
      <li>Macy</li>
      <li v-for='item in navlist'>{{item.name}}</li>
    </ul>
  </div>
</template>
<script>
export default{
  data(){
    return{
      navlist:[{
        name:"导航一",
        href:'www.xxx.com'
      },{
        name:"导航二",
        href:'www.xxx.com'
      },{
        name:"导航三",
        href:'www.xxx.com'
      }]
    }
  }
}
</script>
<style scoped>

</style>
