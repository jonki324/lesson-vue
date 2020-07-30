<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <b-container>
      <b-alert show variant="primary">Bootstrap Vue</b-alert>
      <b-table striped hover :items="users"></b-table>
    </b-container>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      users: []
    }
  },
  mounted() {
    this.$axios.get('http://localhost:3000/users')
    .then((res) => {
      this.users = res.data
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
