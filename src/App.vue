

<template>
<form @submit.prevent="createPost">
<h1>kkccc</h1>
<label for="userId"></label>
<input type="text" id="userId" v-model="formData.userId">
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
        userId: ''

      }
    }
  },
  methods: {
    createPost () {
        axios.post('https://api.poffigu.ru/invite', this.formData)
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
