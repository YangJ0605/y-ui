<template>
  <div id="app">
    <!-- <y-switch v-model="active"></y-switch>
    <y-switch v-model="active" active-color='green' inactive-color='red'></y-switch>
    <y-switch v-model="active" name='gender' ref='xx'></y-switch>
    <hr>
    <y-radio label='0' v-model="gender" name='gender'>男</y-radio>
    <y-radio label='1' v-model="gender" name='gender'>女</y-radio>
    <y-radio label='0' v-model="gender"></y-radio>
    <y-radio label='1' v-model="gender"></y-radio>
    <hr>
    <y-radio-group v-model="gender">
      <y-radio label='0'></y-radio>
      <y-radio label='1'></y-radio>
    </y-radio-group> -->
    <!-- <y-checkbox v-model="active">水果</y-checkbox>
  <hr>
  <y-checkbox-group v-model="arr">
     <y-checkbox  label='水果'></y-checkbox>
     <y-checkbox  label='蔬菜'></y-checkbox>
  </y-checkbox-group> -->
  <y-radio-group v-model="gender">
      <y-radio label='0'></y-radio>
      <y-radio label='1'></y-radio>
    </y-radio-group>
    <y-radio label='1' v-model="gender"></y-radio>
    <y-checkbox v-model="active">水果</y-checkbox>
  <y-form  :model='model' :rules='rules'>
    <y-form-item label='用户名：' prop='username'>
      <y-input v-model="model.username"></y-input>
    </y-form-item>
    <y-form-item label='密码：' prop='password'>
      <y-input v-model="model.password" type='password'></y-input>
    </y-form-item>
  </y-form>
  <test></test>
  <y-button @click="toast">Toast</y-button>
  </div>
</template>

<script>
import Test from './test'
import 'element-ui/lib/theme-chalk/index.css'
import { Message } from 'element-ui'

export default {
  name: 'App',
  components: {Test},
  beforeCreate() {
    console.log(this.gender)
    console.log('father beforeCreated')
  },
  created() {
    console.log(this.gender)
    console.log('father created')
  },
  beforeMount() {
    console.log(this.gender)
    console.log('father beforeMount')
  },
  mounted() {
    console.log(this.gender)
    console.log('father mounted')
    Message({message:'elemessage',duration:0, type:'error'})
  },
  data() {
    return {
      active: 0,
      gender:'1',
      arr: ['水果','蔬菜'],
      model: {
        username: '',
        password: ''
      },
      rules: {
        username:[{ required: true, message: '请输入姓名', trigger: 'blur' },
                  { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
        ],
        password: [{required: true, message: '请输入密码', trigger: 'blur' }]
      }
    }
  },
  methods: {
    toast() {
      this.$toast('这是toast',{position:'bottom',autoClose:false, type:'error'})

      // this.$toast('这是toast',{position:'bottom',autoClose:false, closeButton:null})
    }
  }
};
</script>

<style lang="scss" scoped>
#app {
  margin: 200px 200px;
  button {
    margin-left: 10px;
    margin-bottom: 10px;
  }
}
</style>
