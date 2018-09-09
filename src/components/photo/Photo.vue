<template>
        <div>   
        <common-header bg = "black"> 
                      <span slot="title">Photo </span>
        </common-header>
        <router-view></router-view>

        <common-footer bg = "black"> </common-footer>

    </div>
</template>
<script>
import Axios from "axios";
import CommonFooter from "../common/Footer";
import CommonHeader from "../common/Header";
export default {
  components: { CommonFooter, CommonHeader }
};
</script>
<style scope>
</style>

