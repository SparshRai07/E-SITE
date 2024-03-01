<template>
   <div>
  <h1> i am login page </h1>
   </div>
</template>






<script setup>

import { useAuthStore } from "~/store/auth";
import { ref } from 'vue';
import { useRouter } from 'vue-router';
const authStore = useAuthStore();

const router = useRouter();
const userData = ref({
  email: '',
  password: '',
});
 

const login = async () => {
  try {
    await authStore.login(userData.value); // Await the login action
    redirectToHomepage();
  } catch (error) {
    console.error(error);
  }
};

const redirectToHomepage = () => {
  router.push('/');
};

// definePageMeta({
//   layout: "login",
// });
</script>

<style lang="scss" scoped>
.back-button {
  margin-top: 10px;
  transition: background-color 0.3s, color 0.3s;
}

.back-button:hover {
  background-color: red;
  color: white;
}

</style>