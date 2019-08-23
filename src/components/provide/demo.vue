<template>
    <div>
        <!-- <h1>{{title}}</h1>
        <demo-item></demo-item>
        <button class="btn btn-danger" @click="showHide(true)">
            显示消息提示框
        </button>
        <button class="btn btn-danger" @click="showHide(false)">
            隐藏消息提示框
            </button> -->
        <z-form :form="form" :validate="validate">
            <z-form-item label="用户名" name="username">
                <input type="text" class="form-control "
                id="username" v-model="form.username">
            </z-form-item>
            <z-form-item label="邮箱" name="email">
                <input type="text" class="form-control "
                id="email" v-model="form.email">
            </z-form-item>
            <z-form-item>
                <button type="submit" class="btn btn-primary">提交</button>
            </z-form-item>
        </z-form>
    </div>
</template>

<script>
// import demoItem from "./demo-item";
import zForm from "./z-form";
import zFormItem from "./z-form-item";
export default {
    // inject:['show','showHide'],
    components:{
        // demoItem
        zForm,zFormItem
    },
    data(){
        return{
            // title:"我是父组件的标题"
            form:{
                username:"",
                email:""
            },
            validate:[
                {
                    name:"username",
                    validate:{
                        required:{
                            data:true,
                            msg:"用户名不能为空"
                        },
                        rule:{
                            data:"username",
                            msg:"用户名格式错误"
                        }

                    }
                },
                {
                    name:"email",
                    validate:{
                        required:{
                            data:true,
                            msg:"邮箱不能为空"
                        },
                        rule:{
                            data:"email",
                            msg:"邮箱格式错误"
                        }
                    }
                },

            ]

        }
    },
    methods:{
        // rename(data){
        //     this.title=data;
        // }
    },
    provide(){
        // return{
        //     title:this.title,
        //     rename:this.rename,
        // }
    }
}
</script>

<style>

</style>