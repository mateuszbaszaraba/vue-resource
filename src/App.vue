<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 offset-sm-2 col-md-4 offset-md-6 col-lg-4 offset-lg-4 mt-5">
        <h1>Http</h1>

        <div class="form-group">
          <label>Username</label>
          <input class="form-control" type="text" v-model="user.username"/>
        </div>

        <div class="form-group">
          <label>E-mail</label>
          <input class="form-control" type="text" v-model="user.email" />
        </div>

        <button class="btn btn-primary" @click="submit">Submit</button>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        username: '',
        email: ''
      }
    }
  },
  methods: {
    submit() {
      console.log(this.user)
    }
  }
}
</script>

<style>
</style>
