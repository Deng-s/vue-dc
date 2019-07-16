<template>
  <div class="login">
    <div class="login-box">
      <div class="ava-box">
        <img src="./login1.jpeg" alt="">
      </div>
       <!-- 登录表单区域 -->
        <el-form :model="login" ref="loginRef"  label-width="0px" class="login_form" :rules="loginRules">
        <!-- 用户名 -->
        <el-form-item prop="username">
          <el-input v-model="login.username" prefix-icon="iconfont icon-user" ></el-input>
        </el-form-item>
        <!-- 密码 -->
        <el-form-item prop="password" >
          <el-input v-model="login.password"  prefix-icon="iconfont icon-3702mima" type="password" ></el-input>
        </el-form-item>
        <!-- 按钮区域 -->
        <el-form-item class="btns">
          <el-button type="primary" >登录</el-button>
          <el-button type="info" @click="loginref" >重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>
<script>
export default {
  data:()=>({
    login:{
      username:"admin",
      password:"123456"
    },
    loginRules:{
      username:[
         { required: true, message: '请输入登录账号', trigger: 'blur' },
         { min: 3, max: 10, message: '账号长度在 3 到 10 个字符', trigger: 'blur' }
      ],
       password:[
         { required: true, message: '请输入登录密码', trigger: 'blur' },
         { min: 6, max: 15, message: '密码长度在 6 到 15 个字符', trigger: 'blur' }
      ]
    }
  }),
  methods:{
    loginref(){    
      this.$refs.loginRef.resetFields()
      this.login.username=this.login.password=""
    }
  }
};
</script>
<style lang="less" scoped>
.login {
  height: 100%;
  background: #2b4b6b;
  .login-box {
    width: 450px;
    height: 300px;
    background-color: #fff;
    border-radius: 3px;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);

    .ava-box {
      height: 130px;
      width: 130px;
      border: 1px solid #eee;
      border-radius: 50%;
      padding: 10px;
      box-shadow: 0 0 10px #ddd;
      position: absolute;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: #fff;
      img {
        width: 100%;
        height: 100%;
        border-radius: 50%;
        background-color: #eee;
      }
  }

  }

  .login_form {
  position: absolute;
  bottom: 0;
  width: 100%;
  padding: 0 20px;
  box-sizing: border-box;
  }

.btns {
  display: flex;
  justify-content: flex-end;
}   
}
</style>