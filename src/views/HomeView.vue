<template>
  <div>
    <div class="tc pd10">
      <i class="iconfont">&#xe613;</i>
      <div>new demo</div>
      <div>{{ title }}</div>
    </div>
    <div class="menus">
      <!-- 脚手架的v-for需要一个不重复的key属性 -->
      <el-link type="primary" style="margin: 10px" v-for="d in menus" @click="toPage(d.url)" :key="d.url">{{ d.text }}</el-link>
    </div>
    <button @click="visible = true">登录</button>
    <login-view v-if="visible"></login-view>
    <div id="map" style="width: '800px'; height: '800px'"></div>
  </div>
</template>

<script>
import LoginView from './LoginView.vue'
export default {
  name: 'HomeView',
  data() {
    return {
      title: '￥myweb￥',
      menus: [{ url: '/views/LoginView', text: '登录' }],
      visible: false,
    }
  },

  components: {
    LoginView,
  },
  methods: {
    // vue路由api跳转页面
    toPage(url) {
      this.$router.push(url)
    },
    getMap() {},
  },
}
</script>
<style scoped>
.menus a {
  margin: 1rem;
}
</style>
