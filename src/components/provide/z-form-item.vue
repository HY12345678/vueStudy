<template>
    <div class="form-group">
        <label for="name">{{label}}</label>
        <slot />
        <div class="invalid-feedback">
            用户名不能为空
        </div>
    </div>
</template>

<script>
export default {
    props:['label','name'],
    //接受父组件注入的属性
    inject:['form','validate']
}
</script>

<style>

</style>