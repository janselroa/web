<template>
  <div class="container">
    <div class="id">
      {{id}}
    </div>
    <img v-bind:src="require('../assets/img/'+portada)" alt="">
    <div class="info">
      <h2>{{titulo}}</h2>
      <p>{{autores.join(", ")}}</p>
    </div>
    
  </div>

</template>

<script>

export default {
  name: 'App',
    props:["titulo","portada", "autores","id"]
  
}
</script>

<style scoped>
img{
  width: 60px;
  height: 60px;
  margin-right:15px
}
.container{
  display:flex;
  margin: 15px 0;
}
h2{
  margin:0
}
.id{
  display:flex;
  justify-content:center;
  align-items: center;
  width:30px;
  margin-right:10px;
  font-size: 20px
}
.info{
  display:flex;
  flex-direction:column;
}
.info p{
  margin:0
}
</style>
