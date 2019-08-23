<template>
  <div>
      <!-- 局部：监听通讯（只能当前组件使用） -->
      <button class="btn btn-primary" @click="test">点击通讯</button>


    <demo-item></demo-item>
    <demo-item></demo-item>
    <demo-item></demo-item>
  </div>
</template>

<script>
import demoItem from "./demo-item"
export default {
    components:{
        demoItem
    },
    provide(){
        return{
            $_demo:this
        }
    },
    mounted(){
        //开启一个监听事件
        this.$on('test',(e)=>{
            console.log(e);
        })
    },
    methods:{
        test(){
            //通知test事件
            this.$emit('test',{
                value:'点击通讯'
            })
        }
    }

}
</script>

<style>

</style>