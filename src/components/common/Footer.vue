<template>
  <ul class="footer"  :style="{background:bg}">
    <li> <router-link to="/movie/movieLIst/">电影</router-link> </li>
    <li><router-link to="/music">音乐</router-link> </li>
    <li><router-link to="/book">书籍</router-link> </li>
    <li><router-link to="/photo/photoList">图片</router-link> </li>
  </ul>
</template>

<script>
export default{
  props:['bg']
}
</script>


<style scoped>
.footer{
  height: 1rem;
  background-color: rgb(33,150,2243);
  position: fixed;
  width:100%;
  bottom:0;
  display:flex;
  line-height: 1rem;
  font-size:0.5rem;
}
.footer li{
  flex-grow:1;
  text-align: center;
  color:#fff;
}
.footer li a{
  color:#ccc;
}
.footer a.router-link-active{
  color:#fff;
}
</style>