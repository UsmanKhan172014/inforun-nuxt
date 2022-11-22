<template>
  <div class="container ">
    <div class="row mt-4 justify-content-center">
      <div class="col-md-6 ">
        <div class="card">
          <div class="card-header">
            <h3 class="card-title">Login</h3>
          </div>
          <div class="card-body">
                <div class="form-group">
                    <label>Email</label>
                    <input type="email" class="form-control" placeholder="Enter Your email">
                </div>
                <div class="form-group">
                    <label>Password</label>
                    <input type="password" class="form-control" placeholder="Enter your password">
                </div>

                <div class="form-group mt-2">
                    <NuxtLink class="btn btn-primary" to="/">Login</NuxtLink>
                </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginPage',

    data() {
        return {
        email: '',
        password: '',
        }
    },
    methods: {
        login() {
            this.$store.dispatch('login', {email: this.email, password: this.password})
        }
    }
}

</script>
