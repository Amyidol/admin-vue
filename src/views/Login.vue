<template>
    <div class="login">
    <el-form ref="form" :model="form" class="container" :rules="rules">
      <el-form-item>
        <div class="avatar">
          <img src="../assets/avatar.jpg" alt="">
        </div>
      </el-form-item>
      <el-form-item prop="username">
        <el-input v-model="form.username" placeholder="账户" prefix-icon="myicon myicon-user"></el-input>
      </el-form-item>
      <el-form-item prop="password">
        <el-input v-model="form.password" placeholder="密码" prefix-icon="myicon myicon-key" type="password"></el-input>
      </el-form-item>
      <el-form-item label="">
        <el-button type="primary" class="login-btn" @click="loginSubmit('form')">登录</el-button>
      </el-form-item>
    </el-form>

    </div>
</template>
<script>
export default {
data () {
   return {
       form: {
        username: '',
        password: ''
      }, 
    rules: {
        username: [
          { required: true, message: '请输入用户名', trigger: 'blur' }
        ],
        password: [
          { required: true, message: '请输入密码', trigger: 'blur' }
        ]
      }
   } 
}
}
</script>
<style lang="scss" scoped>
.login {
  position: fixed;
  width: 100%;
  height: 100%;
    background:#616161 url(../assets/bg.jpg) center/cover no-repeat;
//   background: linear-gradient(-45deg, #2158d3 ,#f857a6);
  .container {
	width: 400px;
	box-shadow:0 15px 35px rgba(0,0,0,0.4);
	position:absolute;
	left: 0;
	right: 0;
    transition: .4s, box-shadow .3s .4s;
    padding: 0px 40px 15px 40px;
    margin: 200px auto;
    background: rgba(71, 71, 71, 0.8);
    .avatar {
      position: relative;
      left: 50%;
      width: 150px;
      height: 150px;
      margin-left: -60px;
      margin-top: -60px;
      box-sizing: border-box;
      border-radius: 50%;
      border: 5px solid #fff;
      box-shadow: 0 1px 5px #ccc;
      overflow: hidden;
      img{
          width: 100%;
          height: 100%;
      }
    }
    .login-btn {
      width: 100%;
      border: none;
    background: linear-gradient(-45deg, #2158d3 ,#f857a6);
    }
  }
}
</style>
