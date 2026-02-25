<script>
  const api_key = {
    data(){
      return {
        selected_course: "",
        moodle_data:[]
      }
    },

    created(){
      this.moodleAPI()
    },

    computed(){
      select_course();
    },

    methods: {
      async moodleAPI(){
        let api = await fetch('https://lms.mironpingel.dk')
        this.moodle_data = await api.json()
      },
      async select_course(){
        let selected_course = ""
        selected_subcourse: [
          {course: "", sub_course: ""},
        ]
      }
    }
  }
  export default api_key;
</script>
