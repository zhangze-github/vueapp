<template>
	<div  class="movie-list">
		<ul >
			<li @click = "goDetail(movie.id)" v-for="movie in moveList" :key="movie.id" class="movie">
				<div ><img :src="movie.images.large" alt=""></div>	
				<div>
					<p class="movie-img">{{movie.title}}</p>
					<p class="movie-info"> {{movie.year}}</p>
				</div>
			</li>
		</ul>
		<div class="loading" v-show="loadingShow">
			<img src="../../assets/img/5-121204193934.gif" alt="">
		</div>
		<div class="tip" v-show="tip">
			<h4>数据已经到底了</h4>
		</div>
	</div>
</template>
<script>
import Axios from "axios";
export default {
  data() {
    return {
      moveList: [],
      loadingShow: true,
      tip: false
    };
  },
  mounted() {
    this.loadDate();
    window.onscroll = () => {
      let cH = document.documentElement.clientHeight;
      let sT = document.documentElement.scrollTop;
      let sH = document.documentElement.scrollHeight;
      //  console.log(cH,sT,sH);
      if (cH + sT == sH) {
        //  console.log('123');
        this.loadingShow = true;
        if (!this.tip) {
          this.loadDate();
        } else {
          this.loadingShow = false;
        }
      }
    };
  },
  methods: {
    loadDate() {
      Axios.get(
        API_PROXY +
          "https://api.douban.com/v2/movie/in_theaters?apikey=0b2bdeda43b5688921839c8ecb20399b&city=%E5%8C%97%E4%BA%AC&count=100&start=" +
          this.moveList.length
      )
        .then(res => {
          console.log(res);
          let data = res.data.subjects.slice(
            this.moveList.length,
            this.moveList.length + 10
          );
          if (data.length < 10) {
            this.tip = true;
          }
          this.moveList = this.moveList.concat(data);
          this.loadingShow = false;

          // console.log(this.moveList);
        })
        .catch(() => {});
    },
       goDetail(movieId){
   	  console.log(movieId);
    	   this.$router.push('/movie/movieDetail/'+ movieId);
      }
  }
}
</script>

<style scoped>
.movie-list {
  margin: 1rem 0;
  margin-bottom: 1rem;
}
.movie {
  display: flex;
  padding: 0, 0.2rem;
  border-bottom: solid 1px black;
}
.movie-img {
  flex-grow: 1;
}
.movie-img img {
  width: 100%;
}
.movie-info {
  flex-grow: 2;
}
.loading {
  text-align: center;
}
.tip {
  text-align: center;
}
</style>

