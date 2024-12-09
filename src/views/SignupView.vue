
<template>
  <div class="SignUpScreen">
    <div class="SignUp">
      <h1>SignUp</h1>
      <FloatLabel variant="on">
        <InputText id="username" v-model="userName" />
        <label for="username">Username</label>
      </FloatLabel>
      <br>
      <FloatLabel variant="on">
          <Password v-model="passWord" inputId="password" toggleMask />
          <label for="password">Password</label>
      </FloatLabel>
      <br>
      <FloatLabel variant="on">
          <Password v-model="confirmPassword" inputId="confirmPassword" toggleMask />
          <label for="confirmPassword">Confirm Password</label>
      </FloatLabel>
      <br>
      <FloatLabel variant="on">
        <InputText id="email" v-model="email" />
        <label for="email">Email</label>
      </FloatLabel>
      <p>Have account? <a href="login">Login</a></p>
      <Button type="submit" v-on:click="SignUp()" severity="secondary" label="SignUp" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Password from 'primevue/password';
import FloatLabel from 'primevue/floatlabel';
import InputText from 'primevue/inputtext';
import Button from 'primevue/button';
import axios from 'axios';
const userName = ref(null);
const passWord = ref(null);
const confirmPassword = ref(null);
const email = ref(null);

const SignUp = async () => {
  console.log(userName.value)
  console.log(passWord.value)
  console.log(confirmPassword.value)
  console.log(email.value)
  if (passWord.value !== confirmPassword.value) {
      alert('Password Not Matched')
  }
  const response = await axios.get('http://localhost:3000/users', {
      userName: userName.value,
      passWord: passWord.value,
      email: email.value
  });
  try {
    if( response.status === 200){
      alert('User Created Successfully')
      window.location.href = '/login'
    }
    alert('User Creation Failed')
  } catch (error) {
    alert('Something Went Wrong')
  }
}

</script>
<style scoped>
.SignUpScreen{
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
background-image: url('https://cdn.pixabay.com/photo/2015/12/06/20/10/christmas-bauble-1079926_640.jpg');
width: 100%;
justify-content: center;
align-items: center;
display: flex;
height: 100vh;
}
.SignUp{
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
background-color: rgba(255, 255, 255, 0.795);
height: 70%;
width: 25%;
border-radius: 50px;
}
h1{
font-size: 50px;
margin-bottom: 5%;
}
#username{
width: 235px;
}
#email{
width: 235px;
}
p{
font-size: 18px;
}
a{
text-decoration: none;
}
</style>

<template>
  <div class="SignUpScreen">
    <div class="SignUp">
      <h1>SignUp</h1>
      <FloatLabel variant="on">
        <InputText id="username" v-model="userName" />
        <label for="username">Username</label>
      </FloatLabel>
      <br>
      <FloatLabel variant="on">
          <Password v-model="passWord" inputId="password" toggleMask />
          <label for="password">Password</label>
      </FloatLabel>
      <br>
      <FloatLabel variant="on">
          <Password v-model="confirmPassword" inputId="confirmPassword" toggleMask />
          <label for="confirmPassword">Confirm Password</label>
      </FloatLabel>
      <br>
      <FloatLabel variant="on">
        <InputText id="email" v-model="email" />
        <label for="email">Email</label>
      </FloatLabel>
      <p>Have account? <a href="login">Login</a></p>
      <Button type="submit" v-on:click="SignUp()" severity="secondary" label="SignUp" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Password from 'primevue/password';
import FloatLabel from 'primevue/floatlabel';
import InputText from 'primevue/inputtext';
import Button from 'primevue/button';
import axios from 'axios';
const userName = ref(null);
const passWord = ref(null);
const confirmPassword = ref(null);
const email = ref(null);

const SignUp = async () => {
  console.log(userName.value)
  console.log(passWord.value)
  console.log(confirmPassword.value)
  console.log(email.value)
  if (passWord.value !== confirmPassword.value) {
      alert('Password Not Matched')
  }
  const response = await axios.get('http://localhost:3000/users', {
      userName: userName.value,
      passWord: passWord.value,
      email: email.value
  });
  try {
    if( response.status === 200){
      alert('User Created Successfully')
      window.location.href = '/login'
    }
    alert('User Creation Failed')
  } catch (error) {
    alert('Something Went Wrong')
  }
}

</script>
<style scoped>
.SignUpScreen{
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
background-image: url('https://cdn.pixabay.com/photo/2015/12/06/20/10/christmas-bauble-1079926_640.jpg');
width: 100%;
justify-content: center;
align-items: center;
display: flex;
height: 100vh;
}
.SignUp{
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
background-color: rgba(255, 255, 255, 0.795);
height: 70%;
width: 25%;
border-radius: 50px;
}
h1{
font-size: 50px;
margin-bottom: 5%;
}
#username{
width: 235px;
}
#email{
width: 235px;
}
p{
font-size: 18px;
}
a{
text-decoration: none;
}
</style>
