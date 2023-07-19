<template>
  <div class="modal" :class="isActive">
    <div class="modal-background"></div>
   <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Agregar curso</p>
      <button   @click="closeModal" 
                class="delete" aria-label="close"></button>
    </header>
    <section class="modal-card-body">
   
      <!-- Content ... -->
        <div class="field">
            <label class="label">Nombre</label>
            <div class="control">
                <input class="input" type="text" >
            </div>
        </div>
        <div class="field">
            <label class="label">URL de la imagen</label>
            <div class="control">
                <input class="input" type="text" >
            </div>
        </div>
        <div class="field">
            <label class="label">Cupos del curso</label>
            <div class="control">
                <input class="input" type="text" >
            </div>
        </div>
        <div class="field">
            <label class="label">Inscritos en el curso</label>
            <div class="control">
                <input class="input" type="text" >
            </div>
        </div>
        <div class="field">
            <label class="label">Duración del curso</label>
            <div class="control">
                <input class="input" type="text" >
            </div>
        </div>
        <div class="field">
            <label class="label">Fecha de registro</label>
            <div class="control">
                <input class="input" type="text" >
            </div>
        </div>
        <div class="field">
            <label class="label">Costo del curso</label>
            <div class="control">
                <input class="input" type="text" >
            </div>
        </div>
        <div class="field">
            <label class="label">Descripcion</label>
            <div class="control">
                <textarea class="textarea" ></textarea>
            </div>
        </div>

    </section>
    <footer class="modal-card-foot">
      <button class="button is-success">Agregar Curso</button>
      <button 
          @click="closeModal" 
           class="button">Cancelar</button>
    </footer>
  </div>
        
        


  </div>
</template>

<script>
export default {
    data(){
        return{
        }
    },
    props:['isActive'],

    methods:{
        closeModal(){
            this.$emit('close-modal')    
        
        }
    },

}
</script>

<style>

</style>