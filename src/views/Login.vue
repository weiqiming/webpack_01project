<template>
  <div class="login">
    <!-- :是v-bind,是给表单绑定自定义属性,v-bind是在data中去定义一个对象 -->
    <el-form  ref='form' :model="form" class="container" :rules="rules">
      <el-form-item>
        <div class="avatar">
          <img src="../assets/avatar.jpg" alt="">
        </div>
      </el-form-item>
      <!-- prop是element-ui里面封装好的,需要校验就要写 -->
      <el-form-item prop="username">
        <el-input v-model="form.username" placeholder="账户" prefix-icon="myicon myicon-user"></el-input>
      </el-form-item>
      <el-form-item prop="password">
        <el-input  v-model="form.password" placeholder="密码" prefix-icon="myicon myicon-key" type="password"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" class="login-btn" >登录</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>


<script>
export default {
  data(){
    // 这里用return就是将data里面的对象返回给函数来使用
      return {
        form:{
          username:'',
          password:''
        },
        rules:{
          username:[
            // required是非空,trigger是失去焦点
              {required:true,message:' 请输入用户名',trigger:'blur'},
          ],
          password:[
            {required:true,message:' 请输入密码',trigger:'blur'}
          ]
        }
      }
  }
}
</script>
<style>
 .login {
  position: fixed;
  width: 100%;
  height: 100%;
  background-color: #2f4050;
}
 .login .container {
    position: absolute;
    left: 0;
    right: 0;
    width: 400px;
    padding: 0px 40px 15px 40px;
    margin: 200px auto;
    background: white;
 }
.login .container .avatar {
      position: relative;
      left: 50%;
      width: 120px;
      height: 120px;
      margin-left: -60px;
      margin-top: -60px;
      box-sizing: border-box;
      border-radius: 50%;
      border: 10px solid #fff;
      box-shadow: 0 1px 5px #ccc;
      overflow: hidden;
    }
.login .container .login-btn {
      width: 100%;
    }

</style>


