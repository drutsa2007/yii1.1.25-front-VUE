<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
</template>

<script>
import axios from 'axios'
axios.defaults.withCredentials = true;
const config = {
	headers: {
		'Accept': 'application/json',
	}
}

const apiClient = axios.create({
	baseURL: 'http://yii/index.php',
	withCredentials: true,
	headers: config.headers,
});


export default {
  data() {
    return {
    }
  },
  created() {
    apiClient.get('/json')
      .then(function (response) {
        console.log(response);
      })
  },
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
