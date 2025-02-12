<template>
    <main class="login__main">
      <h1>LoginPage</h1>
      <form @submit.prevent="submitHandler">
        <section>
          <article>
            <label for="email">Email</label>
            <input
              v-model="email"
              type="email"
              id="email"
              placeholder="votre email"
              maxlength="320"
            />
          </article>
          <article>
            <label for="password">Mot de passe</label>
            <input
              v-model="password"
              type="password"
              id="paswword"
              placeholder="votre mot de passe"
            />
          </article>
        </section>
        <section>
          <button type="submit">Se connecter</button>
          <button type="reset">Réintialiser</button>
        </section>
      </form>
    </main>
  </template>
  
  <script setup lang="ts">
import { watch, reactive, ref } from "vue";
import inputValidator from "../utils/input-validator";
/*const data = reactive({
  email: "",
  password: "",
  //errorMessage: ""
});*/

const email = ref("");
const password = ref("");

watch(email, (val) => {
        console.log(val, inputValidator(val,'email'))
    
});

watch(password, (val) => {
        console.log(val, inputValidator(val,'password'))
    
});
/*
watch(data, (val) => {
  console.log(val);
});

const isUserInputValid = (input: string): boolean => {
  const pattern = new RegExp(/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/);
  return pattern.test(input);
};

const submitHandler = () => {
  if (isUserInputValid(data.email)) {
    console.log("Email est valide");
    data.errorMessage = ""; // Clear any previous error message
  } else {
    console.log("Email pas valide");
    data.errorMessage = "Adresse email invalide. Veuillez entrer une adresse email valide.";
  }
};*/

const submitHandler = () => {
};

const inputHandler = () => {};
</script>