<template>
<div class="modal" :class="isActive">
    <div class="modal-background"></div>
   <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Editar curso</p>
      <button @click="closeModal" 
              class="delete" aria-label="close"></button>
    </header>
    <section class="modal-card-body">
   
      <!-- Content ... -->
        <div class="field">
            <label class="label">Nombre</label>
            <div class="control">
                <input class="input" type="text" 
                    v-model="nombre">
            </div>
        </div>
        <div class="field">
            <label class="label">URL de la imagen</label>
            <div class="control">
                <input class="input" type="text" 
                    :value="$store.getters.curso(courseId).img">
            </div>
        </div>
        <div class="field">
            <label class="label">Cupos del curso</label>
            <div class="control">
                <input class="input" type="text" 
                 :value="$store.getters.curso(courseId).cupos">
            </div>
        </div>
        <div class="field">
            <label class="label">Inscritos en el curso</label>
            <div class="control">
                <input class="input" type="text" 
                  :value="$store.getters.curso(courseId).inscritos">
            </div>
        </div>
        <div class="field">
            <label class="label">Duración del curso</label>
            <div class="control">
                <input class="input" type="text"
                  :value="$store.getters.curso(courseId).duracion">
            </div>
        </div>
        <div class="field">
            <label class="label">Fecha de registro</label>
            <div class="control">
                <input class="input" type="text" 
                  :value="$store.getters.curso(courseId).fecha_registro">
            </div>
        </div>
        <div class="field">
            <label class="label">Costo del curso</label>
            <div class="control">
                <input class="input" type="text" 
                  :value="$store.getters.curso(courseId).costo">
            </div>
        </div>
        <div class="field">
            <label class="label">Descripcion</label>
            <div class="control">
                <textarea class="textarea" 
                    :value="$store.getters.curso(courseId).descripcion"></textarea>
            </div>
        </div>

    </section>
    <footer class="modal-card-foot">
      <button class="button is-success">Guardar cambios</button>
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
            nombre:$store.getters.curso(courseId).nombre
        }
    },
    props:['isActive','courseId'],

    methods:{
        closeModal(){
            this.$emit('close-modal')    
        
        },
        saveChanges(){

        }
    },

}
</script>

<style>

</style>