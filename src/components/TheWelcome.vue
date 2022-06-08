<script>

import axios from 'axios'
axios.defaults.withCredentials = true;
const config = {
	headers: {
		'Accept': 'application/json',
	}
}

const apiClient = axios.create({
	baseURL: 'http://yii/index.php/',
	withCredentials: true,
	headers: config.headers,
});


export default {
  name: 'auth',
  data() {
    return {
      form: {
        email: '',
        password: '' 
      }
    }
  },
  methods: {
    signIn() {
      apiClient.post('/login/index', {
        email: this.form.email,
        password: this.form.password
      })
      .then(function (response) {
        console.log(response);
      })     
    }
  }
}
</script>

<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <form @submit.prevent="signIn">
          <h1 class="h3 mb-3 fw-normal">Please sign in</h1>

          <div class="form-floating">
            <input type="email" class="form-control" id="floatingInput" placeholder="name@example.com" v-model="form.email">
            <label for="floatingInput">Email address</label>
          </div>
          <div class="form-floating">
            <input type="password" class="form-control" id="floatingPassword" placeholder="Password" v-model="form.password">
            <label for="floatingPassword">Password</label>
          </div>

          <div class="checkbox mb-3">
            <label>
              <input type="checkbox" value="remember-me"> Remember me
            </label>
          </div>
          <button class="w-100 btn btn-lg btn-primary" @click="qwe">Sign in</button>
          <p class="mt-5 mb-3 text-muted">&copy; 2017вЂ“2022</p>
        </form>
      </div>
    </div>
  </div>
</template>

<style>
@import '@/assets/css/bootstrap.css';
</style>