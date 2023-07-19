<template>
  <div>
    
        

        <button @click="addCourse"
                class="button is-primary is-medium mb-4">
                agregar curso</button>
       
        <AddCourseModal 
            @close-modal="closeAddModal"
             :isActive="showAddModal"/>

        <table class="table is-fullwidth">
            <thead>
                <th>ID</th>
                <th>Nombre</th>
                <th>Cupos</th>
                <th>Inscritos</th>
                <th>Duracion</th>
                <th>Costo</th>
                <th>Terminado</th>
                <th>Fecha</th>
                <th colspan="2"></th>
            </thead>
            <tr v-for="curso,idx in $store.state.cursos" :key="`curso-${idx}`">
                <th>{{curso.id}}</th>
                <td>{{curso.nombre}}</td>
                <td>{{curso.cupos}}</td>
                <td>{{curso.inscritos}}</td>
                <td>{{curso.duracion}}</td>
                <td>{{curso.costo}}</td>
                <td>{{curso.completado}}</td>
                <td>{{curso.fecha_registro}}</td>
                <td><button class="button" 
                        @click="editar($event,curso.id)">editar</button></td>
                <td><button class="button"
                            @click="eliminar($event,curso.id)"    >
                    eliminar</button></td>
            </tr>
        </table>

        <div class="px-6">
            <div class="notification is-info">Cantidad total de alumnos permitidos: {{$store.getters.alumnosPermitidos}}</div>
            <div class="notification">Cantidad total de alumnos inscritos: {{$store.getters.alumnosInscritos}} </div>
            <div class="notification">Cantidad total de cupos restantes: {{$store.getters.cuposRestantes}} </div>
            <div class="notification">Cantidad total de cursos terminados: {{$store.getters.cantCursosTerminados}}</div>
            <div class="notification">Cantidad total de cursos activos: {{$store.getters.cantCursosActivos}} </div>
            <div class="notification">Cantidad total de cursos: {{$store.getters.cantTotalCursos}}</div>

        </div>

            
              <EditModal @close-modal="closeEditModal" 
                        :isActive="showEditModal"
                        :courseId="courseId" />
              
              <DeleteModal @close-modal="closeDeleteModal" 
                        :isActive="showDeleteModal"
                        :courseId="courseId" />
                        
        
        

    
  </div> 

</template>

<script>
import EditModal from '@/components/EditModal.vue'
import AddCourseModal from '@/components/AddCourseModal.vue'
import DeleteModal from '@/components/DeleteModal.vue'

export default {
    data(){
        return{
           showEditModal:'',
           showAddModal:'',
           showDeleteModal:'',
           courseId:''
        
        }
    },
    methods:{
        editar(e, id){
            e.preventDefault()
            this.showEditModal='is-active'
            this.courseId = id

        },

        closeEditModal(){
            this.courseId=''
            this.showEditModal=""
        },
        closeAddModal(){
            this.showAddModal=""
        },
        closeDeleteModal(){
            this.courseId=''
            this.showDeleteModal=""
        },
        
        addCourse(e){
            e.preventDefault()
            this.showAddModal='is-active'
        },
        eliminar(e, id){
            e.preventDefault()
            this.showDeleteModal='is-active'
            this.courseId = id

        }
    },
    components:{
        EditModal,
        AddCourseModal,
        DeleteModal
    }
}
</script>

<style>

</style>