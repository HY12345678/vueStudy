<template>
    <div class="pt-5">

        <div class="card" >
            <div class="card-body">
                {{title}}
            </div>
        </div>
        <button class="btn btn-primary" type="button" @click="clickEvent">
            子组件
        </button>
    </div>
</template>

<script>
export default {
    inject:['title','rename'],
    methods:{
        clickEvent(){
            this.rename("我是子组件派来修改你的")
        }
    }
}
</script>

<style>

</style>