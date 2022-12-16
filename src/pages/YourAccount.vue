<template>

<div>
    <h1 v-if="useUserStore().user">Hello {{useUserStore().user.email}} ! 👋</h1>

    <h3 class="account-h3">Your Account:</h3>

    <div class="accounttabla" >
        
            <div class="user-update">
                <div>
                    <label for="username">Name</label>
                    <input id="username" type="text" v-model.lazy="username" />
                </div>
                <div>
                    <label for="usersurname">Surname</label>
                    <input id="username" type="text" v-model="usersurname" />
                </div>
                <div>
                    <label for="email">Email</label>
                    <input id="username" type="email" v-model="email" />
                </div>
                <div>
                    <input
                    type="submit"
                    class="button-update"
                    :value="loading ? 'Loading ...' : 'Update'"
                    :disabled="loading"/>
                </div>
            </div>
        
    </div>
</div>




</template>

<script setup>
import { useRouter } from "vue-router";
import { useUserStore } from "../store/user.js";
import { computed, readonly } from "vue";
import { ref } from 'vue';






</script>

<style>

</style>