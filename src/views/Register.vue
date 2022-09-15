<template>
  <main class="form-signin w-100 m-auto">
    <form>
      <h1 class="h3 mb-3 fw-normal">Please register</h1>

      <div class="form-floating">
        <input type="text" class="form-control" placeholder="Username">
        <label>Username</label>
      </div>

      <div class="form-floating">
        <input type="email" class="form-control" placeholder="name@example.com">
        <label>Email address</label>
      </div>

      <div class="form-floating">
        <input type="password" class="form-control" placeholder="Password">
        <label>Password</label>
      </div>

      <div class="form-floating">
        <input type="password" class="form-control" placeholder="Password Confirm">
        <label>Password Confirm</label>
      </div>

      <button class="w-100 btn btn-lg btn-primary" type="submit">Submit</button>
      <p class="mt-5 mb-3 text-muted">&copy; 2022–2023</p>
    </form>
  </main>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Register"
}
</script>

<style scoped>

</style>