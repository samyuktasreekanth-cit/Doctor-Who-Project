<template>
    <div>
        <nav>
            <ul>
                <li><router-link to="/" exact>Explore</router-link></li>
                <li><router-link to="/add" exact>Add Content</router-link></li>
            </ul>
        </nav>
        
        <header id="dw-header">
            <img src="./title.png">
        </header>

    </div>
</template>

<script>

export default {
  data () {
    return {
        title: 'Doctor Who'
    }
  }
}
</script>

<style>

img{
    width:35%;
    margin-left: 20px;
}
ul{
    list-style-type: none;
    text-align: center;
    margin: 0;
}
li{
    display: inline;
    margin: 0 10px;
}
a{
    color: #fff;
    text-decoration: none;
    padding: 6px 8px;
    border-radius: 10px;
}
nav{
    background: black;
     opacity: 75%;
    padding: 14px 0;
    margin-bottom: 40px;
    margin-left: 150px;
    margin-right: 150px;
}
.router-link-active{
    background:#eee;
    color: #444;
}
</style>

