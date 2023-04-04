<template>
  <h2>REGISTER</h2>
  <form @submit.prevent="handleSubmit">
    <div>
      <label for="name">Name</label>
      <input type="text" name="name" id="name" v-model="user.name" />
    </div>
    <div>
      <label for="email">Email</label>
      <input type="email" name="email" id="email" v-model="user.email" />
    </div>
    <div>
      <label for="password">Password</label>
      <input
        type="password"
        name="password"
        id="password"
        v-model="user.password"
      />
    </div>
    <div>
      <button>Login</button>
    </div>
  </form>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      user: {
        email: "",
        password: "",
        name: "",
      },
    };
  },
  methods: {
    async handleSubmit() {
      try {
        
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>
<style scoped>
form {
  width: 100%;
}
form div {
  width: 100%;
  margin: 0 auto;
  height: 30px;
  margin-bottom: 20px;
}
form div input {
  width: 50%;
}
form div label,
form div button {
  width: 20%;
}
</style>
