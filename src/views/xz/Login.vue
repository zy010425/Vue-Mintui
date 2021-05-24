<template>
  <div>
      <!-- 学子商城的一些功能实现.... -->
      <h3>用户登录</h3>
      <mt-field label="用户名" placeholder="请输入用户名" v-model="uname"></mt-field>
      <mt-field label="密码" placeholder="请输入密码"  v-model="upwd"></mt-field>
      <mt-button type="primary" @click="login">登录</mt-button>
  </div>
</template>

<script>
// import axios from "axios"
// axios.defaults.baseURL="http://localhost:5050";

import {Login} from "@/assets/js/apis/user.js"//导入接口
export default {
    data(){
        return {
            uname:"dingding",
            upwd:"123456",
        }
    },
    methods:{
       async login(){
            var uname = this.uname;
            var upwd = this.upwd;

            //要对数据是进行验证 uname upwd


           var reg = /^[a-z0-9]{3,12}$/i; //正则表达式
           // 验证用户名 不合格提示后返回
           if(!reg.test(uname)){
               this.$messsagebox("错误","用户名格式不正确")
               return;
           }
           // 验证用户密码
           if(!reg.test(upwd)){
               this.$messsagebox("错误","用户密码格式不正确")
               return;
           }
            var user={uname,upwd};
            this.$indicator.open({
                text:"加载中....",
                spinnerType:"fading-circle"
            })
         let result = await Login(user);
        this.$indicator.close();
        //   console.log(result=>{
                // console.log(result);
                // this.$router.push("/product")
            // })
            if(result.code==200){
                //登录成功跳转商品列表
                 //console.log(result);测试返回值
                this.$router.push("/product")
            }else{
                this.$messagebox("404",result.msg)
            }

        }
    }
}
</script>

<style>

</style>