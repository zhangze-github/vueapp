<template>
        <div>   
        <common-header bg = "green"> 
             <span slot="title">Music</span>

        </common-header>
        
        <router-view> </router-view>
        <common-footer bg = "green"> </common-footer>

    </div>
</template>
<script>
import CommonFooter from "../common/Footer";
import CommonHeader from "../common/Header";
export default {
  components: { CommonFooter, CommonHeader }
};
</script>
<style scope>
</style>

