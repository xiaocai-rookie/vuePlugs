<template>
  <div id="app">
  	<!--<router-view></router-view>-->
	  	 <my-headr></my-headr>
  </div>
</template>

<script>
import myHeadr from './components/Header1.vue';
export default {
  name: 'app',
  //子组件中组建的注册方式
  components:{myHeadr}
}

</script>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
