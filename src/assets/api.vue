<script>
  const api_key = {
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
  export default api_key;
</script>
