<template>
  <div class="users">
<ul>
<li v-for="user in users" v-on:click="user.show=!user.show">
      <h2> {{user.name}}</h2>
      <h3 v-show="user.show">{{user.position}}</h3>
</li>
</ul>
  </div>
</template>
<script>
export  default{
 name:'users',
 props:["users"],
 data(){
 return{
 }
 },
 methods:{
    changeTitle:function(){
    this.$emit("titleChanged","子向父传值");
    }

 }
}
</script>
<style scoped>
.users{
 width:100%;
 max-width:1200px;
 margin:40px auto;
 padding:0 20px;
 box-sizing:border-box;
}
ul{
 display:flex;
 flex-grow:wrap;
 list-style-type:none;
 padding:0;
}
li{
 flex-grow:1;
 flex-basis:200px;
 text-align:center;
 padding:30px;
 border:1px solid #222;
 margin:10px;
}
</style>
