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
                    v-model="editedCourse.nombre"/>
            </div>
        </div>
        <div class="field">
            <label class="label">URL de la imagen</label>
            <div class="control">
                <input class="input" type="text" 
                   v-model="editedCourse.img" >
            </div>
        </div>
        <div class="field">
            <label class="label">Cupos del curso</label>
            <div class="control">
                <input class="input" type="text" 
                  v-model="editedCourse.cupos">
            </div>
        </div>
        <div class="field">
            <label class="label">Inscritos en el curso</label>
            <div class="control">
                <input class="input" type="text" 
                  v-model="editedCourse.inscritos" >
            </div>
        </div>
        <div class="field">
            <label class="label">Duración del curso</label>
            <div class="control">
                <input class="input" type="text"
                  v-model="editedCourse.duracion">
            </div>
        </div>
        <div class="field">
            <label class="label">Fecha de registro</label>
            <div class="control">
                <input class="input" type="text" 
                  v-model="editedCourse.fecha_registro">
            </div>
        </div>
        <div class="field">
            <label class="label">Costo del curso</label>
            <div class="control">
                <input class="input" type="text" 
                  v-model="editedCourse.costo">
            </div>
        </div>
        <div class="field">
            <label class="label">Descripcion</label>
            <div class="control">
                <textarea class="textarea" 
                    v-model="editedCourse.descripcion"></textarea>
            </div>
        </div>

    </section>
    <footer class="modal-card-foot">
      <button @click="saveChanges"
                class="button is-success">Guardar cambios</button>
      <button 
          @click="closeModal" 
           class="button">Cancelar</button>
    </footer>
  </div>
        
        


  </div>
</template>

<script>
export default {
    props:['isActive','courseId'],
    data(){
        return{
            editedCourse:{
                id: '',
                img: '',
                nombre: '',
                costo:'',
                duracion:'',
                cupos:'',
                inscritos:'',
                completado:'',
                fecha_registro:'',
                descripcion:''
            }
          
        }
    },

    methods:{
        closeModal(){
          
            this.$emit('close-modal')    
        
        },
        saveChanges(){
            this.$store.commit('editCourse',this.editedCourse)
           
            this.$emit('close-modal')    
        },
        editValue(value){
            alert(value)
        }  
    },
    watch:{
        courseId(){
            this.editedCourse.id  = this.$store.getters.curso(this.courseId).id
            this.editedCourse.img = this.$store.getters.curso(this.courseId).img
            this.editedCourse.nombre = this.$store.getters.curso(this.courseId).nombre
            this.editedCourse.costo = this.$store.getters.curso(this.courseId).costo
            this.editedCourse.duracion = this.$store.getters.curso(this.courseId).duracion
            this.editedCourse.cupos = this.$store.getters.curso(this.courseId).cupos
            this.editedCourse.inscritos = this.$store.getters.curso(this.courseId).inscritos
            this.editedCourse.completado = this.$store.getters.curso(this.courseId).completado
            this.editedCourse.fecha_registro = this.$store.getters.curso(this.courseId).fecha_registro
            this.editedCourse.descripcion = this.$store.getters.curso(this.courseId).descripcion
                
        },
      
        
    }
  

}
</script>

<style>

</style>