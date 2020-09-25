<template>
<div id="overall">
    <div id="add-blog">
        <h2>Add New Content</h2>
        <form v-if="!submitted">
            <label>Device Name:</label>
            <input type="text" v-model='blog.device_name' required/>

            <label>Episode No:</label>
            <input type="text" v-model='blog.ep_no' required/>

            <label>Episode Name:</label>
            <input type="text" v-model='blog.ep_name' required/>

            <label>Details:</label>
            <textarea v-model='blog.details'></textarea>

            <button v-on:click.prevent="post">SUBMIT</button>
        </form>

        <div v-if="submitted">
            <h3>Thanks for adding your post</h3>
        </div>

        <div id="preview">
            <h1>{{blog.device_name}}</h1>
            <p>Episode No: {{blog.ep_no}}</p>
            <p>Episode Name: {{blog.ep_name}}</p>
            <p>{{blog.details}}</p>
        </div>

        
    </div>
</div>

</template>

<script>

export default {
  data () {
    return {
        blog:{
            device_name:'', 
            ep_no:'', 
            ep_name:'', 
            details:''
        }, 
        submitted: false
    }
  }, 
  methods:{
      post:function(){
          this.$http.post('https://myvueproject-firebase.firebaseio.com/posts.json', this.blog).then(function(data){
              this.submitted = true;
          });
      }
  }
}
</script>

<style>
#overall{
     max-width: 80%;
    margin: 30px auto; 
    background-color: black; 
    opacity: 75%; 
    padding: 20px 0px;
}

#add-blog *{
    box-sizing: border-box;
}
#add-blog{
    margin: 20px auto;
    max-width: 650px;
}
#add-blog h2{
    color: White;
}
label{
    display: block;
    margin: 20px 0 10px;
    font-weight: bold;
    font-size: 18px;
    color: White;
}

input[type="text"],textarea{
    width: 100%;
    padding: 8px;
}

#preview{
    padding: 10px 20px;
    border: 1px solid white;
    margin: 30px 0;
}
textarea{
    width: 100%;
    height: 200px;
}
h1{
    text-align: center;
}

button{
    padding: 5px;
    width: 20%;
    margin: 30px auto;
}


</style>

