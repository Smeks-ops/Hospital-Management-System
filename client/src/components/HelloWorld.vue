/* eslint-disable semi */ /* eslint-disable */
<template>
  <div>
    <h1>Register</h1>

    <input type="email" name="email" v-model="email" placeholder="email" />
    <br />
    <input
      type="password"
      name="password"
      v-model="password"
      placeholder="password"
    />
    <br />
    <button @click="register">
      Register
    </button>
  </div>
</template>

<script>
import AuthenticationService from "@/services/AuthenticationService";
export default {
  // eslint-disable-next-line quotes

  // eslint-disable-next-line space-before-function-paren
  data() {
    return {
      // eslint-disable-next-line quotes
      email: "",
      password: ""
      // eslint-disable-next-line semi
    };
  },
  mounted() {},
  methods: {
    async register() {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      });
      console.log(response.data);
    }
  }
  // eslint-disable-next-line semi
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
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
