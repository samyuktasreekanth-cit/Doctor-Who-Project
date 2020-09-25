<template>
    <footer>
        <p>{{copyright}}</p>
    </footer>
</template>

<script>

export default {
  data () {
    return {
        copyright: '@Samyukta Sreekanth'
    }
  }
}
</script>

<style>
footer{
  background: black;
  opacity: 75%;
    padding: 15px 0;
    margin-bottom: 40px;
}
p{
  text-align: center;
  color: white;
  font-weight: bold;
}
</style>

