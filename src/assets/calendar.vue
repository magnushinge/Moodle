<template>
  <div id="calendarContainer">
    <section id="dayLabels">
      <p>M</p>
      <p>T</p>
      <p>W</p>
      <p>T</p>
      <p>F</p>
      <p>S</p>
      <p>S</p>
    </section>
    <section id="days" >
      <p v-for="n in 28" :key="n">{{ n }}</p>
    </section>
  </div>

</template>
 
<style>
  @import './calendar.css';
</style>


<script>
  export default {
    data(){
      return {
      }
    },
  }
</script>
