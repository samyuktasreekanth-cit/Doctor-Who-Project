<template>
  <div>
    <app-header></app-header>

    <router-view></router-view>

    <app-footer></app-footer>
    
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import addBlog from './components/addBlog.vue';
import showBlogs from './components/showBlogs.vue';

export default {
  components:{
    'app-header': Header, 
    'app-footer' : Footer, 
    'add-blog' : addBlog, 
    'show-blogs': showBlogs
  }, 
  data () {
    return {
    }
  }
}
</script>

<style>
body{
  background: url(bill.jpg) no-repeat fixed; 
   background-size: 100%;
      
}

img{
  height: 250px;
  
}



</style>

   /* background-image: url("dw.jpg");
  background-repeat: no-repeat;
  background-size: 100%;
  background-color: black; */

        