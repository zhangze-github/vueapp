<template>
    <div class="header" :style="{background:bg}">
        <button @click="goHome" class="home">首页</button>
        <h2 class="title">
            <slot name="title">默认值</slot>
        </h2>
    </div>

</template>

<script>
export default{
    methods:{
        goHome(){
            this.$router.push('/')
        }
    },
    props:['bg']
}
</script>


<style scoped>
.header{
    height:1rem;
    background-color: rgb(33,150,243);
    position: fixed;
    top: 0;
    width: 100%;
    line-height: 1rem;
}
.home{
    color:#fff;
    background-color:rgba(33, 149, 243, 0);
    font-size: 0.5rem;
    height: 1rem;
    position: relative;
    top:-0.2rem;
}
.title{
    position: absolute;
    top:50%;
    left:50%;
    transform: translate(-50%,-50%);
    color:#fff;
}


</style>