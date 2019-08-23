<template>
  <div id="app" class="container p-5">
      <!-- <div class="alert alert-primary" v-show="show">
        消息提示
      </div> -->
      <!-- $refs案例 -->
      <!-- <demo-ref></demo-ref> -->

      <!-- provide案例 -->
      <!-- <demo-provide></demo-provide> -->

      <!-- $on与$emit案例 -->
      <!-- <demo-on-emit></demo-on-emit> -->

      <!-- 自定义组件v-model案例 实现v-model双向绑定-->
            <demo-vmodel></demo-vmodel>
  </div>
</template>

<script>
// import demoRef  from "@/components/ref-parent-children/demo.vue";
// import demoProvide  from "@/components/provide/demo.vue";
// import demoOnEmit  from "@/components/on-emit/demo.vue";
import demoVmodel  from "@/components/v-model/demo.vue";
export default {
  name: 'app',
  components: {
    // demoRef
    // demoProvide
    demoVmodel
    // demoOnEmit
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
