<template>

</template>

<script>
import {ref} from "vue";
import axios from "axios";
export default {
  data() {
    return {
      daftarsurah: ref([])
    }
  },
  mounted() {
    this.getDaftarSurah()
  },
  methods: {
    getDaftarSurah() {
      axios.get("https://api.quran.com/api/v4/chapters?language=id")
          .then((respons) =>
          {
            console.timeLog(respons)
            this.daftarsurah = respons.data.chapters
          })
          .catch((err) =>
          {
            console.log('error' + err)
          })
    }
  }
}
</script>

<style scoped>
li {
  list-style: none;
  text-align: left;
}

</style>