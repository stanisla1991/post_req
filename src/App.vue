

<template>
<form @submit.prevent="createPost">
<h1>kkccc</h1>
<label for="email"></label>
<input type="text" id="email" v-model="formData.email">
<button>Пригласить</button>
</form>
</template>



<script>
import axios from 'axios';

export default {
  name: 'CreatePost',
  data() {
    return {
      formData: {
        email: '',

      }
    }
  },
  methods: {
    createPost () {
        axios.post(
          `https://api.poffigu.ru/invite`, this.formData)
          .then(response => console.log(response))
          .catch(error => console.log(error))
    },
  }
}
</script>






<style scoped>
h1 {
  color: blue;
}
</style>
