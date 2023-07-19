<template>
  <div>
    <CourseCard 
      v-for="curso,index in $store.state.cursos" :key="`curso-${index}`"
      :curso=curso
    />
  </div>
</template>

<script>
// @ is an alias to /src
import CourseCard from '@/components/CourseCard.vue'

export default {
  name: 'HomeView',
  components: {
    CourseCard,
  }
}
</script>
