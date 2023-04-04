<template>
  <h2>LOGIN</h2>
  <form @submit.prevent="handleSubmit">
    <div>
      <label for="email">Email</label>
      <input type="email" name="email" id="email" v-model="email" />
    </div>
    <div>
      <label for="password">Password</label>
      <input
        type="password"
        name="password"
        id="password"
        v-model="matkhau"
      />
    </div>
    <div>
      <input type="submit" value="Login" />
    </div>
  </form>
</template>

<script>
import {ref} from "vue";
import axios, { Axios } from "axios";
import {useRouter} from "vue-router";
export default {
  setup() {
    const email = ref("");
    const matkhau = ref("");
    const router = useRouter();
    async function handleSubmit() {
      try{
        const response = await axios.post("http://localhost:3000/users/login",{
        email: email.value,
        password: matkhau.value
      })
      console.log(response.data.message)
      if(response.data.message != "success" ){
        alert(response.data.message);
      }else{
        localStorage.setItem("token",response.data.token);
        router.push("/");
      }
      }catch(e){
        console.log(e);
      }
      
      
    }
    return {
      handleSubmit,
      email,matkhau
    }
  }
    
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
