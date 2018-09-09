<template>
    <div class="detail">
        <div class="detail-content">
            <div class="detail-img">
                <img :src="detail.images.large" alt="">
            </div>
            <div class="detail-info">
                <h3 v-text="detail.original_title"></h3>
            </div>
        </div>
        <div>
            <h3>简介</h3>
            <h2 v-text="detail.summary"></h2>
        </div>
    </div>

</template>
<script>
import Axios from "axios";
export default {
    data(){
        return{
            detail:{}
        }
    },
  mounted() {
    Axios.get(API_PROXY +
      "http://api.douban.com/v2/movie/subject/" + this.$route.params.movieId
    ).then(res => {
      console.log(res);
      this.detail = res.data;
    //   console.log(this.detail.images.large);
    });
  }
};
</script>
<style scoped>
.detail {
  margin: 1rem 0;
  padding: 0 0.2rem;
}
.detail-content {
  display: flex;
}
.detail-img {
  flex-grow: 1;
  width: 0;
}
.detail-info {
  flex-grow: 2;
  width: 0;
}
img{
    width:100%;
}


</style>

