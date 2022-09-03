<template>
  <div>
    <div class="top-barr">
      <p class="numeral">#</p>
      <p class="titulo">TITULO</p>
      <p>Album</p>
    </div>
    
  </div>
 <div class="container">
  <div>
    <cancion v-for="cancion in canciones" :titulo="cancion.titulo" :portada="cancion.portada" 
      :autores="cancion.autores" :key="cancion.id" :id="cancion.id"
    />
  </div>
  <div class="albumes">
    <p v-for="album in albumes" :key="album">{{album}}</p>
  </div>
 </div>
</template>

<script>
import dataCanciones from "./assets/conciones.js"
import cancion from "./components/cancion"
import {ref} from "vue"
export default {
  name: 'App',
  components: {
    cancion
  },
  setup(){
    const canciones = ref(dataCanciones)
    const albumes = ref(canciones.value.map(n=>n.album))
    return {canciones,albumes}
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Lato&display=swap');

html{
  color-scheme: dark;
  font-family: 'Lato', sans-serif;

}
.top-barr{
  margin-bottom: 40px;
  border-bottom: 1px solid #333;
  display: flex;
}

p,.id{
  color: #aaa;
}p,h2{
  text-transform: capitalize;
}
p.titulo{
  margin-right: 500px;
  margin-left: 20px
}
.container{
  display: flex
}
.albumes{
  margin-left:30px
}
.albumes>p{
  font-size: 20px;
  margin:30px 0;
}
</style>
