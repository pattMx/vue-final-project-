<script setup>
import { useRouter } from "vue-router";
import { useUserStore } from "../store/user.js";
import { computed, readonly } from "vue";
import { ref } from 'vue';

const router = useRouter();
const userStore = useUserStore();

// boton signout
async function signOut() {
  try {
    router.push({ path: "/auth" });
    userStore.signOut();
  } catch (e) {
    alert(e);
  }
}

const changeBoolean = ref (false);
const toggle = () => {
  changeBoolean.value = !changeBoolean.value;
};

</script>

<template>
  
  <nav>
    <ul class="licontent"> 
      <li>
        <router-link to="/" class="router-link">
          Task Manager
        </router-link>
      </li>

      <li>
        <router-link to="/YourAccount" class="router-link">
          Your Account
        </router-link>
      </li>
      </ul>

      <div>
        <ul>
          <li class="welcomenavbar">
            <p v-if="useUserStore().user">Welcome {{useUserStore().user.email}}</p>
          </li>
          <li>
            <a id="signout" class="button-red" @click="signOut">Sign Out</a>
          </li>
        </ul>
      </div>

      <button @click="toggle" class="toggle"></button>
      <div v-show="changeBoolean" class="hambuguermenu">
        <ul>
          <li>
            <router-link to="/" class="router-link-cel">
          Task Manager</router-link>
          </li>
          <li>
            <router-link to="/" class="router-link-cel">
          Your Account</router-link>
          </li>
          <li>
            <a id="signout" class="button-red-cel" @click="signOut">Sign Out</a>
          </li>
        </ul>
      </div>
  </nav>
</template>

<style scoped>

</style>
