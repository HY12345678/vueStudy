<template>
    <div>

        <h1 class="text-center">{{ val }}</h1>
        <e-input v-model='val'></e-input>
    </div>

</template>

<script>
import eInput from "./e-input"
export default {
    components:{
        eInput
    },
    data(){
        return{
            val:'请输入用户名'
        }
    }
}
</script>

<style>

</style>