<template>
  <div id="app">
    <!-- <Header></Header> -->
    <!-- enter-active-class="animated bounceInRight"
      leave-active-class="animated bounceOutLeft" -->
  <!--   <router-link
      :to="{ name: 'login' }"
      v-if="!$route.meta.isShow"
      @click.native="removeuser"
      >退出登录</router-link
    > -->
    <!-- 在 link中 添加点击事件的时候 需要加.native -->
    <bottomNav v-if="!$route.meta.isShow"></bottomNav>
    <!--  <transition
      mode="out-in"
      name="custom-classes-transition"
      enter-active-class="animated bounceInRight"
      leave-active-class="animated bounceOutLeft"
    > -->
    <router-view></router-view>
    <!-- </transition> -->
  </div>
</template>

<script>
//
//底部自由导航组件
import bottomNav from "./components/footer/bottomnav";
import router from "./router/index";
// import Header from './components/header/Herder.vue';
// import { Button } from 'vant'

export default {
  /*  data() {
    return {
      isShow: true,
    };
  }, */
  methods: {
    removeuser() {
      localStorage.removeItem("username");
      this.$router.push("/login");
    },
  },
  watch: {
    $route() {
      console.log(this.$route);
      this.isShow = this.$route.meta.isShow;
    },
  },
  name: "App",
  components: {
    bottomNav,
  },
  router,
};
</script>

<style>
element.style {
}
<style > .hd .img[data-v-172bb70c] {
  margin: 0 0.16rem 0 0.32rem;
  width: 0.96rem;
  height: 0.96rem;
  overflow: hidden;
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
  border-radius: 100%;
  border: 3px solid hsla(0, 0%, 100%, 0.4);
  text-align: center;
}
* {
  background-repeat: no-repeat;
  padding: 0;
  margin: 0;
}
*,
:after,
:before {
  box-sizing: inherit;
}
user agent stylesheet div {
  display: block;
}
.app-shell .app-view-wrapper .app-view[data-v-bc186c1a] {
  background: #fff;
  color: #3c3c3c;
}

#app,
body,
html {
  font-size: 52.1111px;
}
* {
  margin: 0;
  padding: 0;
}
.v-enter,
.v-leave {
  transform: translateX(100%);
}
.v-enter-active,
.v-leave-active {
  transition: all 0.8s;
}
/* .bounceInRight,.bounceOutLeft{
  transition:all 0.8s;
} */
/* :root {
  --animate-duration: 100ms;
  --animate-delay: 0.1s;
} */
#app {
  height: 100vh;
}
body {
  height: 100%;
}
</style>
