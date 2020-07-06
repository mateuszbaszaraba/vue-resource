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
        <button class="btn btn-primary" @click="fetchData">Get Data</button>

        <ul class="list-group">
          <li class="list-group-item" v-for="u in users" :key="u.id">{{ u.username }} | {{ u.email }}</li>
        </ul>

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
      },
      users: []
    }
  },
  methods: {
    submit() {
      this.$http.post('', this.user)
        .then(response => {
          console.log(response)
        }, error => {
          console.log(error)
        })
    },
    fetchData() {
      this.$http.get('')
        .then(response => {
          return response.json();
        })
        .then(data => {
          const resultArray = [];
          for (let key in data) {
            resultArray.push(data[key])
          }
          this.users = resultArray
        })
    }
  }
}
</script>

<style>
</style>
