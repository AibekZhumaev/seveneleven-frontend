<template>
  <main class="form-signin w-100 m-auto">
    <form @submit.prevent="submit">
      <h1 class="h3 mb-3 fw-normal">Create account</h1>

      <div class="form-floating">
        <input v-model="data.username" class="form-control" placeholder="Username">
        <label>Username</label>
      </div>

      <div class="form-floating">
        <input v-model="data.email" type="email" class="form-control" placeholder="name@example.com">
        <label>Email address</label>
      </div>

      <div class="form-floating">
        <input v-model="data.password" type="password" class="form-control" placeholder="Password">
        <label>Password</label>
      </div>

      <div class="form-floating">
        <input v-model="data.password_confirm" type="password" class="form-control" placeholder="Password Confirm">
        <label>Password Confirm</label>
      </div>

      <button class="w-100 btn btn-lg btn-primary" type="submit">Submit</button>
      <p class="mt-5 mb-3 text-muted">&copy; 2022–2023</p>
    </form>
  </main>
</template>

<script lang="ts">
import {reactive} from "vue";
import axios from "axios"
import { useRouter } from "vue-router";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Register",
  setup() {
    // eslint-disable-next-line @typescript-eslint/no-unused-vars
    const data = reactive({
      username: '',
      email: '',
      password: '',
      password_confirm: ''
    });
    const router = useRouter()

    const submit = async () => {
      await axios.post('http://localhost:8090/api/signup', data);

      await router.push('/signin');
    };
    return {
      data, submit
    };
  }
}
</script>

<style scoped>

</style>