<template>
  <div id="app" class="container p-5">
      <!-- <div class="alert alert-primary" v-show="show">
        消息提示
      </div> -->
      <!-- $refs案例 -->
      <!-- <demo-ref></demo-ref> -->

      <!-- provide案例 -->
      <demo-provide></demo-provide>
  </div>
</template>

<script>
// import demoRef  from "@/components/ref-parent-children/demo.vue";
import demoProvide  from "@/components/provide/demo.vue";
export default {
  name: 'app',
  components: {
    // demoRef
    demoProvide
  },
  data(){
    return{
      // show:false
    }
    
  },
  methods:{
    // showHide(data){
    //   this.show=data;
    // }
  },
  // provide(){
  //   return{
  //     show:this.show,
  //     showHide:this.showHide,
  //   }
  // }
}
</script>

<style>

</style>
