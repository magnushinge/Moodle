<script setup>
  import api_key from '../assets/api.vue';
  /* import { } from 'lucide-vue-next'; */

  defineOptions({
    extends: api_key
  })
</script> 

<template>
  <main>

    <section class="navSection">
      <h1>Courses</h1>
      <article>
        <button @click="">
          {{moodle_data.course_name }}
        </button>
      </article>
    </section>

    <section class="navSection">
    </section>
  </main>
</template>

<script>
  export default = {
    data(){
      return {
      }
    },

    created(){
    },

    methods: {
    }
  }
</script>
