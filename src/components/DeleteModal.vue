<template>
<div class="modal" :class="isActive">
    <div class="modal-background"></div>
   <div class="modal-card">
    <header class="modal-card-head">
      <p class="modal-card-title">Eliminar curso</p>
      <button @click="closeModal" 
              class="delete" aria-label="close"></button>
    </header>
    
    <footer class="modal-card-foot">
      <button @click="deleteCourse"
                class="button is-success">Confirmar</button>
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
           
          
        }
    },

    methods:{
        closeModal(){
          
            this.$emit('close-modal')    
        
        },
        deleteCourse(){
            this.$store.commit('deleteCourse',this.courseId)
           
            this.$emit('close-modal')    
        },
    
    },
    watch:{
       
    }
  

}
</script>

<style>

</style>