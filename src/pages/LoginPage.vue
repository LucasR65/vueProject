<template>
    <main class="login__main">
      <h1>LoginPage</h1>
      <form @submit.prevent="submitHandler">
        <section>
          <article>
            <label for="email">Email</label>
            <input
              v-model="data.email"
              type="email"
              id="email"
              placeholder="votre email"
              maxlength="320"
            />
          </article>
          <article>
            <label for="password">Mot de passe</label>
            <input
              v-model="data.password"
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
import { watch, reactive } from "vue";

const data = reactive({
  email: "",
  password: "",
  errorMessage: ""
});

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
    // Continue with form submission
  } else {
    console.log("Email pas valide");
    data.errorMessage = "Adresse email invalide. Veuillez entrer une adresse email valide.";
    // Show error message to the user
  }
};

const resetForm = () => {
  data.email = "";
  data.password = "";
  data.errorMessage = "";
};

const inputHandler = () => {};
</script>