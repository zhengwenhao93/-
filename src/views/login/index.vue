<template>
  <div class="login-title">
    <div class="navbar">
      <el-form
        :model="LoginForm"
        :rules="LoginfromRules"
        label-width="100px"
        label-position="left"
      >
        <h1 class="weit">火星</h1>

        <div class="login-Nav flex-column">
          <el-form-item ref="LoginfromRules" prop="username">
            <el-input v-model="LoginForm.username"></el-input>
          </el-form-item>

          <el-form-item ref="LoginfromRules" prop="password">
            <el-input v-model="LoginForm.password"></el-input>
          </el-form-item>

          <el-form-item>
            <el-button type="primary" @click="handleLoginSubmit"
              >登录</el-button
            >
          </el-form-item>
        </div>
      </el-form>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue'
const LoginForm = reactive({
  username: '',
  password: ''
})

const LoginfromRules = {
  username: [{ required: true, message: '请输入用户名', trigger: 'blur' }],
  password: [{ required: true, message: '请输入密码', trigger: 'blur' }]
}

const handleLoginSubmit = () => {
  LoginForm.value.validate((valid) => {
    console.log(valid)
  })
}
</script>
<style lang="scss" scoped>
.login-title {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
  background-color: #f9fcff;

  .navbar {
    width: 500px;
    padding: 50px;
    background-color: #fff;
    border-radius: 5px;
    box-shadow: 0 0 10px 5px rgb(199 201 203 / 30%);
    box-sizing: border-box;
    text-align: center;
    .weit {
      font-weight: normal;
      font-size: 50px;
      margin-bottom: 48px;
    }
  }
}
</style>
