<template>
  <div id="app">
    <!-- <NavBar></NavBar> -->
    <transition name="fold">
          <router-view/>
    </transition>
  </div>
</template>

<script>
// import NavBar from "./components/nav" 
import  Config from './config/server'
export default {
  name: 'App',
  // components:{
  //   NavBar
  // },
  data(){
    return {
      Link:Config.baseUrl
    }
  }
}
</script>

<style>
*{
  padding:0px;
  margin:0px;
}
/* ::selection {
background:#6C6;
color:#fff;
} */
html,body{
  background: rgb( 244,247,249);
  height: 100%;
}
a{
  text-decoration: none;
}
i,b{font-style: normal;}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #656565;
  height: 100%;;
}
.Right{
    position: fixed;
    top: 100px;
    right: 40px;
    color: #409EFF;
}
.fold-enter-active {
  animation-name: fold-in;
  animation-duration: .5s;
}
.fold-leave-active {
  animation-name: fold-out;
  animation-duration: .5s;
}
@keyframes fold-in {
  0% {
    transform: translate3d(100%,0 , 0);
    opacity:0;
  }
  50% {
    transform: translate3d(50%, 0, 0);
    opacity: 0.1;
  }
  100% {
    transform: translate3d(0%, 0, 0);
    opacity: 1;
  }
}
@keyframes fold-out {
  0% {
    transform: translate3d(0%, 0, 0);
        opacity:1;
  }
  50% {
    transform: translate3d(-50%, 0, 0);
        opacity:0.5;
  }
  100% {
    transform: translate3d(-100%, 0, 0);
        opacity:0;
  }
}
.el-form-item__content:after,
 .el-form-item__content:before{
   display: none !important;
 }
 .el-form-item:after, 
 .el-form-item:before{
    display: none !important;
 }
 @media screen and (max-width: 768px) {
    .el-dialog{
      width: 99%;
    }
    .el-dialog .el-select{
      width: 100%;
    }
    .el-dialog .el-button{
      width: 100%;
      margin-bottom: 10px;
    }
    .el-dialog .el-button+.el-button{
      margin-left: 0px;
    }
    .el-button+.el-button{
      margin-left: 0px;
    }
}
</style>
