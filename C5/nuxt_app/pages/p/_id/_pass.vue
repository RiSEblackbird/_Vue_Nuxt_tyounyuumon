// 5-8
<template>
  <section class="container">
    <h1>{{ title }}</h1>
    <p v-html="message">no message.</p>
    <hr>
    <div class="right">
      <router-link to="/">Go to Top</router-link>
    </div>
  </section>
</template>

// 5-9
<script>
export default {
  validate ({ params }) {
    if (params.id == undefined || params.pass == underfined) {
      return false;
    } else {
      return true;
    }
  },
  data: function () {
    return {
      title: 'Login'
    };
  },
  computed: {
    message: function () {
      let id = this.$route.params.id != undefined
        ? this.$route.params.id : '*** no id ***';
      let pass = this.$route.params.pass != undefined
        ? this.$route.params.pass : '*** no password ***';
      return 'ID : ' + id + '<br>PASS : ' + pass;
    }
  }
}
</script>

<style>
.container {
  padding: 5px 10px;
}
h1 {
  font-size: 60pt;
  color: #345980;
}
p {
  padding-top: 5px;
  font-size: 20pt;
}
a {
  font-size: 16px;
}
.right {
  text-align: right;
}
</style>