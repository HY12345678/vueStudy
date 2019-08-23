<template>
  <div>

      <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
    inject:['$_demo'],
    data(){
        return{
            msg:"我是子组件"
        }
    },
    mounted(){
        //  this.$on('test',(e)=>{
        //      console.log('demo-item'.e)
        //     this.msg = e.value;
        // })
        this.$_demo.$on('test',(e)=>{
             console.log('demo-item',e)
            this.msg = e.value;
        })
    }

}
</script>

<style>

</style>