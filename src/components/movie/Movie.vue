<template>

    <div>   
        <common-header>
            <span slot="title">Movie </span>
             </common-header>
        <router-view></router-view>

        <common-footer> </common-footer>

    </div>

</template>

<script>
import CommonFooter from "../common/Footer";
import CommonHeader from "../common/Header";
export default {
  components: {CommonFooter, CommonHeader}
};
</script>


<style scoped>
</style>