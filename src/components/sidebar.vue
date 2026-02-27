<script setup>
  import api_key from '../assets/api.vue';
  import { ChevronDown, ChevronLeft, ChevronRight } from 'lucide-vue-next';

  defineOptions({
    extends: api_key
  })
</script> 

<template>
  <nav>
    <section class="navSection">
      <div class="navSectionHead" @click="toggle_section()">
        <span><h1>Courses</h1></span>
        <ChevronDown size="var(--UI-large-icon)" class="chevron-icon" :class="{ 'rotate': !section_open }" />
      </div>
      <div class="navSectionContent" v-if="this.section_open">
        <ul>
          <!-- Ville lave en v-for af courses men API'en har kun 1 course-->
          <li class="navItem" 
            @click='selected_course = moodle_data.course_name' 
            :class="{ 'courseSelected': selected_course === moodle_data.course_name }">
            <span>{{ moodle_data.course_name }}</span>
          </li>
        </ul>
      </div>
    </section>

    <section class="navSection" v-if="selected_course != '' ">
      <div class="navSectionHead">
        <span><h1>{{ selected_course }}</h1></span>
      </div>
      <div class="navSectionContent"> 
        <ul>
          <!-- 
          Jeg ville have taget dem her fra API'en, men de er ikke i den
          Ville have lavet et for loop, med dem. De her 3 er dog i alle courses 
          Så jeg valgte at putte dem ind for at vise hvordan det ville se ud.
          -->
          <li class="navItem"
              @click='selected_subcourse = "Participants"'
              :class="{ 'subcourseSelected': selected_subcourse  === 'Participants' }">
            Participants
          </li>
          <li class="navItem" 
              @click='selected_subcourse = "Competencies"'
              :class="{ 'subcourseSelected': selected_subcourse  === 'Competencies' }">
            Competencies
          </li>
          <li class="navItem" 
              @click='selected_subcourse = "Grades"' 
              :class="{ 'subcourseSelected': selected_subcourse  === 'Grades' }">
            Grades
          </li>

          <div id="monthSelect">
            <ChevronLeft/> January 2026 <ChevronRight/>
          </div>

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
              <p v-for="n in 31" 
              @click="selected_subcourse =  2026-1-n" 
              :key="n"
              :class="{ 'selectedDay': selected_subcourse === 2026-1-n }">
                {{ n }}
              </p>
            </section>
          </div>

          <div id="daySwitch">
            <div id="dayBack">
              <ChevronLeft/><p>Back</p>
            </div>
            <div id="dayForwards">
              <p>Forwards</p><ChevronRight/>
            </div>
          </div>
        </ul>
      
      </div>
    </section>

  </nav>
</template>

<style>
  @import './calendar.css';
  @import './sidebar.css';
</style>

<script>
  export default {
    data(){
      return {
        section_open: true
      }
    },

    created(){
    },
    
    methods: {
      toggle_section(){
        this.section_open = !this.section_open
      },
    }
  }
</script>
