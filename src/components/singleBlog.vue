<template>
        <div id="whole">
        
            <div id="same">
                <div id="single-blog">
                    <h1>{{blog.device_name}}</h1>
                    <p>Episode No: {{blog.ep_no}}</p>
                    <p>Episode Name: {{blog.ep_name}}</p>
                </div>           
            </div>

            <div id="same">
                <article>{{blog.details}}</article>
            </div>
        </div>
</template>

<script>

export default {
  data () {
    return {
        id:this.$route.params.id, 
        blog:{}
    }
  }, 
  created(){
      this.$http.get('https://myvueproject-firebase.firebaseio.com/posts/' + this.id + '.json').then(function(data){
          return data.json();
      }).then(function(data){
          this.blog = data;
      });
  }
}
</script>

<style>

#whole{
    max-width: 85%;
    margin: 0 auto;
    background-color: black;
    opacity: 85%;
    display:flex;
    flex-flow: wrap;
    justify-content:center;
    margin-bottom:30px;
}

#same {
    background: #eee;
    width: 45%;
    margin: 20px;
    text-align: center;
    background: url(mini.jpg);
    opacity: 0.7;
}

#single-blog p{
    color: black;
}

#single-blog h1{
    color: black;
}

#same article{
    text-align: center;
    margin: 30px;
    font-size: 110%;
    font-weight: bold;
}


</style>

