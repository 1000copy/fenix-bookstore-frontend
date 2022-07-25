<template>
<!--  <div class="home-box">-->
    <el-container>
      <button @click="mocktest">mocktest</button>
      <el-header direction-="vertical">
        <NavigationBar/>
      </el-header>
      <el-main>
        <div class="container">
          <router-view></router-view>
        </div>
      </el-main>
      <el-footer>
        <Copyright/>
      </el-footer>
    </el-container>
<!--  </div>-->
</template>

<script>
/* eslint-disable */
import NavigationBar from '@/components/home/NavigationBar'
import Copyright from '@/components/home/Copyright'
import Axios from 'axios'
export default {
  name: 'index.vue',
  components: {
    Copyright,
    NavigationBar
  },
  methods: {
    async mocktest () {
      alert('hi')
      console.error('抛出全局异常');
      this.$throw(new Error('abcd'))
      var a = await Axios.get(`/1/`)
      console.log(a)
       this.$notify({
          title: '标题名称',
          message: 'ab'
        });
    }
  }
}
</script>

<style scoped>
  .container {
    display: block;
    text-align: center;
    margin: 40px;
    width: 1320px;
    height: 100%;
  }
</style>
