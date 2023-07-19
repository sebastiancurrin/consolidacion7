<template>
 
    <!-- <h1>{{curso.nombre}}</h1>
    <img :src="curso.img" alt="">
    <h2>{{curso.costo}}</h2>
    <h2>{{curso.duracion}}</h2>
    <h2>{{curso.cupos}}</h2>
    <h2>{{curso.inscritos}}</h2>
    <h2>{{curso.completado}}</h2>
    <h2>{{curso.fecha_registro}}</h2>
    <h2>{{curso.descripcion}}</h2> -->

<div class="column">
    <div class="card">
      <div class="card-image">
        <figure class="image is-4by3">
          <img :src="curso.img"
            alt="Placeholder image">
        </figure>
      </div>
      <div class="card-content">
        <div class="media">
           <div class="media-content">
            <p class="title is-4">{{curso.nombre}}</p>
            <p class="subtitle is-6">{{curso.descripcion}}</p>
          </div>
        </div>
    
        <div class="content">
            <p>costo: {{curso.costo}}</p>
            <p>duracion: {{curso.duracion}}</p>
            <p>cupos: {{curso.cupos}}</p>
            <p>inscritos: {{curso.inscritos}}</p>
            <p>completado: {{curso.completado}}</p>
            <p>fecha: {{curso.fecha_registro}}</p>
          <time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time>
        </div>
      </div>
    </div>
</div>



</template>

<script>
export default {
    props:['curso']
}
</script>

<style>

</style>