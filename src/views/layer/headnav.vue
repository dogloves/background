<template>
  <div class="header_container">

    <el-breadcrumb separator="/">
      <el-breadcrumb-item :to="{ path: '/home' }">首页</el-breadcrumb-item>
      <el-breadcrumb-item v-for="(item, index) in $route.meta" :key="index">{{item}}</el-breadcrumb-item>
    </el-breadcrumb>
    <el-dropdown @command="handleCommand" menu-align='start'>
      <img :src="adminInfo.avatar" class="avator">
      <el-dropdown-menu slot="dropdown">
        <el-dropdown-item command="home">首页</el-dropdown-item>
        <el-dropdown-item command="signout">退出</el-dropdown-item>
      </el-dropdown-menu>
    </el-dropdown>
  </div>
</template>

<script>
import { setTimeout } from 'timers';


export default {
  data () {
    return {
      adminInfo: {
        avatar: ''
      }
    }
  },
  created () {
    if (!this.adminInfo.id) {
      //this.getAdminData()
    }
  },
  mounted () {
    console.log(this.$route.meta)
  },
  computed: {
  },
  methods: {
    // ...mapActions(['getAdminData']),
    async handleCommand (command) {
      // if (command == 'home') {
      //   this.$router.push('/manage');
      // } else if (command == 'signout') {
      //   const res = await signout()
      //   if (res.status == 1) {
      //     this.$message({
      //       type: 'success',
      //       message: '退出成功'
      //     });
      //     this.$router.push('/');
      //   } else {
      //     this.$message({
      //       type: 'error',
      //       message: res.message
      //     });
      //   }
      // }
      async function getjj () {
        console.log(1)
        await stockPrice()
        console.log(3)
      }
      function stockPrice () {
        console.log(2)
        return new Promise((resolve, reject) => {
          return setTimeout(function () {
            console.log(4)
            resolve()
          }, 300);
        })
      }
      getjj().then(function () {
        console.log(5)
      })
    }
  }
</script>

<style lang="scss" scoped>
.header_container {
  background-color: #eff2f7;
  height: 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-left: 20px;
}
.avator {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  margin-right: 37px;
}
.el-dropdown-menu__item {
  text-align: center;
}
</style>
