<template>
    <div class="wrapper">
        <div class="login">
            <div class="input-wrapper">
                <input onchange="onchangeUserNumber" class="input" type="text" placeholder="用户名" autofocus="true" value=""/>
                <image class="input-img" src="resources/img/login_input_user_img.png"></image>
            </div>
            <div class="input-wrapper">
                <input onchange="onchangeUserPassword" class="input" type="password" placeholder="密码" value=""/>
                <image class="input-img" src="resources/img/login_input_pass_img.png"></image>
            </div>
            <div class="input-wrapper">
                <div class="input-login" onclick="login">
                    <text class="input-login-text">登录</text>
                </div>
            </div>
            <div class="input-wrapper">
                <text class="input-forget" onclick="findPassword">找回密码</text>
                <text class="input-register" onclick="register">立即注册</text>
            </div>
        </div>
        <toast id="toast"></toast>
    </div>
</template>
 
<script>
    module.exports = {
        data:{
            userNumber:'',
            userPassword:''
        },
        methods:{
            onchangeUserNumber:function (event) {
                this.userNumber = event.value;
            },
            onchangeUserPassword:function (event) {
                this.userPassword = event.value;
            },
            /*找回密码*/
            findPassword:function () {
                this.$vm('toast').$emit('toast','Hello,找回密码暂时未开发，后续我们会进行完善。');
            },
            /*注册*/
            register:function () {
                this.$vm('toast').$emit('toast','Hello,注册暂时未开发，后续我们会进行完善。');
            },
            /*处理登录*/
            login: function () {
                if(this.userNumber.length < 1){
                    this.$vm('toast').$emit('toast','请输入手机号');
                    return;
                }else if(this.userPassword.length < 1){
                    this.$vm('toast').$emit('toast','请输入密码');
                }
                console.log('get:11111111111');
                this.$vm('toast').$emit('toast',"登录成功");
            }
        }
    }
</script>
 
<style>
    .wrapper {
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
    }
    .login{
        margin-top: 180px;
    }
    .input-wrapper{
        width: 550px;
        margin-left: 100px;
        margin-right: 100px;
        margin-bottom: 30px;
    }
    .input {
        font-size: 30px;
        height: 80px;
        width: 550px;
        padding-left: 90px;
        padding-top: 15px;
        padding-bottom: 15px;
        border-width:1px;
        border-color: #48c9bf;
        border-radius:10px;
        outline: none;
    }
    .input-img{
        position: absolute;
        top:10px;
        left: 15px;
        width: 60px;
        height: 60px;
    }
    .input-login{
        height: 80px;
        width: 550px;
        background-color: #48c9bf;
        border-radius: 10px;
        margin-top: 40px;
    }
    .input-login-text{
        height: 80px;
        width: 550px;
        text-align: center;
        line-height: 80px;
        color: white;
        font-size: 35px;
    }
    .input-forget{
        position: absolute;
        left: 30px;
        font-size: 30px;
    }
    .input-register{
        position: absolute;
        right: 30px;
        font-size: 30px;
    }
</style>