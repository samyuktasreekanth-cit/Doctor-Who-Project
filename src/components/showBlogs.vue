<template>
    <div id="show-blogs">
        <h1>Explore</h1>
        <div v-for="blog in blogs" class="single-blog">
            <router-link v-bind:to=" '/blog/' + blog.id "><h2>{{blog.device_name | to-uppercase}}</h2></router-link>
            <article>{{blog.details | snippet}}</article>
        </div>
    </div>


</template>

<script>

export default {
  data () {
    return {
        blogs:[]
    }
  }, 
  created(){
      this.$http.get('https://myvueproject-firebase.firebaseio.com/posts.json').then(function(data){
          return data.json();
      }).then(function(data){
          var blogsArray = [];
          for(let key in data){
              data[key].id = key
              blogsArray.push(data[key]);
          }
          this.blogs = blogsArray;
      })
  }
}
</script>

<style>
#show-blogs{
    max-width: 80%;
    margin: 30px auto;
    background-color: black;
    opacity: 85%;
    padding: 20px 0px;
    overflow: hidden;
}
.single-blog{
    max-width: 25%;
    height: 200px;
    margin: 40px 40px 0px 50px;
    padding: 20px;
    box-sizing: border-box;
    /* background:rgb(202, 137, 137); */
    background: url(mini.jpg);
    opacity: 0.75;
    float: left;
}

.single-blog article{
    font-weight: bold;
}
/* .single-blog:hover {
  background: url(live.gif);
} */

.single-blog:hover {
  background: url(mini.jpg);
  opacity: 0.9;
  transform: scale(1.1);
}

h2{
    text-align: center;
    padding: 0px;
    margin: 0px;
    color: black;
}
.single-blog h2:hover {
  background: rgb(133, 69, 138);
  transform: scale(1.1);
  color: white;
}


h1{
    color: white;
    text-align: center;
}

</style>

