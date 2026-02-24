<script setup>
  /* import { } from 'lucide-vue-next'; */
</script> 

<template>
  <main>
    <section class="navSection">
      <h1>Courses</h1>
      <p>{{ moodle_data.course_name }}</p>
    </section>
  </main>
</template>

<script>
  export default {
    data(){
      return {
        moodle_data:[]
      }
    },

    created(){
      this.moodleAPI()
    },

    methods: {
      async moodleAPI(){
        let api = await fetch('https://lms.mironpingel.dk')
        this.moodle_data = await api.json()
      }
    }
  }
</script>
