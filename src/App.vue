<template>
<div id="app">
   <router-view/>
    <FooterGuide v-show="$route.meta.showFooter"/> <!--只有为true的时候才显示底部的条-->
</div>

</template>

<script>
  import {mapActions} from 'vuex'
  import FooterGuide from './components/FooterGuide/FooterGuide.vue'
export default{

   mounted(){
    // this.$store.dispatch('getAddress')
         this.getAddress()
         this.getUserInfo()
  },
   methods:{
       ...mapActions(['getAddress','getUserInfo'])
   },

  components:{
    FooterGuide
  }
}

</script>

<style lang="stylus" rel="stylesheet/stylus">
     .app
       width 100%
       height 100%
       background #f5f5f5
</style>
