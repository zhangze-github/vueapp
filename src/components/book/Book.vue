<template>
        <div>   
        <common-header bg = "orange">
                        <span slot="title">Book</span> 
             </common-header>
        

        <common-footer bg = "orange"> </common-footer>

    </div>
</template>
<script>
import CommonFooter from "../common/Footer";
import CommonHeader from "../common/Header";
export default {
  components: {CommonFooter, CommonHeader}
};
</script>
<style scope>

</style>

