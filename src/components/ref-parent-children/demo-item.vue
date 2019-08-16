<template>
    <div>
        <h2>{{header}}</h2>
        <input type="text" class="form-control" v-model="val" ref="input"
        @input="changeInput"/>
        
    </div>
</template>

<script>
export default {
    data(){
        return{
            header:"标题",
            val: "输入框"
        }
    },
    methods:{
        //input框自动获取焦点
        focus(){
            this.$refs.input.focus();
        },
        //修改标题
        renameHeader(value){
            this.header=value;
        },
        changeInput(e){
            // console.log(e);
            this.$parent.header=e.target.value;
        }
    }
}
</script>

<style>

</style>