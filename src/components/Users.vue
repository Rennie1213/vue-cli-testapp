<template>
  <div class="users container">
    <h1 class="page-header">Users</h1>
      <ul>
        <li v-for="user in users">{{ user.name }}</li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'users',
  data () {
    return {
      users: []  
    }
  },
  methods: {
    fetchCustomers() {
      this.$http.get('https://jsonplaceholder.typicode.com/users')
        .then(function(response) {
          this.users = response.body;
        })
    }
  },
  created: function(){
    this.fetchCustomers();
  }
}
</script>

<style scoped>

</style>
