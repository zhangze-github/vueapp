<template>
    
        <ul class="list clearfix">
            <li v-for="(p , index) in photo" :key="index">
                <router-link :to="'/photo/photoDetail/'+index">
                    <img :src="p.url" alt="">
                </router-link>
            </li>
        </ul>
        
</template>
<script>
import Axios from "axios";
export default {
  data() {
    return {
      photo: []
    }
  },
  mounted() {
    Axios.get(
      "https://bird.ioliu.cn/v1?url=http://wallpaper.apc.360.cn/index.php?c=WallPaperAndroid&a=getAppsByCategory&cid=6&start=0&count=20"
    ).then(res => {
      console.log(res);
      this.photo = res.data.data;
      console.log(this.photo);
    });
  }
};
</script>
<style scoped>
@import url('../../assets/css/common.css');
.list{
    margin:1rem 0;
}
.list li{
    width:50%;
    float: left;
}
.list li img{
    width:100%;
    height :3rem;
}

</style>
