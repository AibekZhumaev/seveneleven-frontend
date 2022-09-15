<template>
  <main class="form-signin w-100 m-auto">
    <form @submit.prevent="submit">
      <h1 class="h3 mb-3 fw-normal">Please sign-in</h1>

      <div class="form-floating">
        <input v-model="data.username" class="form-control" placeholder="username">
        <label for="floatingInput">Username</label>
      </div>

      <div class="form-floating">
        <input v-model="data.password" type="password" class="form-control" id="floatingPassword"
               placeholder="Password">
        <label for="floatingPassword">Password</label>
      </div>

      <button class="w-100 btn btn-lg btn-primary" type="submit">Signin</button>
      <p class="mt-5 mb-3 text-muted">&copy; 2017–2022</p>
    </form>
  </main>
</template>

<script>
import {reactive} from "vue";
import axios from "axios";
import {useRouter} from "vue-router";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Login",

  setup() {
    const data = reactive({
      username: '',
      password: ''
    });
    const router = useRouter()
    const submit = async () => {
      const response = await axios.post('http://localhost:8090/api/signin', data, {withCredentials: true});

      axios.defaults.headers.common['Authorization'] = `Bearer ${response.data.token}`;

      await router.push('/')
    }

    return {
      data,
      submit
    }
  }
}
</script>

<style scoped>

</style>