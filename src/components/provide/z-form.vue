<template>
  <form>
      <slot />
  </form>
</template>

<script>
export default {
    props:['form','validate'],
    //依赖注入到子组件
    provide(){
        return{
            form:this.form,
            validate:this.validate
        }
    }
}
</script>

<style>

</style>