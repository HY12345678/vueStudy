<template>
    <div class="form-group">
        <label for="name">{{label}}</label>
        <slot />
        <div :class="status===1 ? 'valid-feedback' :'invalid-feedback'">
            {{msg}}
        </div>
    </div>
</template>

<script>
let rules={
    username:/^[a-zA-Z0-9_-]\w{4,16}$/,
    email: /^([a-zA-Z]|[0-9])(\w|\-)+@[a-zA-Z0-9]+\.([a-zA-Z]{2,4})$/
}
export default {
    props:['label','name'],
    //接受父组件注入的属性
    inject:['form','validate'],
    data(){
        return{
            valis:{},
            msg:"验证失败",
            status:0,   //0失败，1成功
            elm:''
            
        }
    },
    //页面渲染完成后
    mounted(){
        //拿到插槽对应的输入框
        // console.log(this.$slots.default[0])
        let el=this.$slots.default[0]
        if(!el) return;
        console.log(el.elm)
        this.elm = el.elm;
        //初始化验证规则
        this.validate.forEach((v) => {
            if(v.name === this.name){
                this.valis = v.validate;
            }
        });
        //监听字段变化
        this.$watch(`form.${this.name}`,(newValue,oldValue)=>{
            // console.log(newValue,this,name);
            //验证数据是否合法
            //1、验证是否必填
            if(this.valis.required.data){
                if(newValue === ''){
                    //给当前的element添加一个class
                    this.actionEvent(false,this.valis.required.msg);
                    return;
                }
            }
            //2、验证其它规则
            if(this.valis.rule && this.valis.rule.data){
    
                let currentRule = rules[this.valis.rule.data] ? rules[this.valis.rule.data] :this.valis.rule.data;
                if(!currentRule.test(newValue)){
                    return this.actionEvent(false,this.valis.rule.msg);
                }
            }

            //成功提示
            this.actionEvent(true,'验证通过')
        })
    },
    methods:{
        actionEvent(action,msg){
            let status = action;
            let obj = {
                status:status ? 1:0,
                before:status ? 'is-invalid' : 'is-valid',
                after:status ? 'is-valid' : 'is-invalid'
            }
            this.status=obj.status;
            this.msg = msg;
            //判断当前状态
            if(this.elm.className.indexOf(obj.after)>-1) return
            //判断之前状态
             if(this.elm.className.indexOf(obj.before)>-1)
                  return this.elm.className = this.elm.className.replace(obj.before,obj.after);

            this.elm.className +=' '+obj.after;
           
        }

    }
}
</script>

<style>

</style>