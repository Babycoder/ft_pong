<template>
  <div>
  
  <Navbar />
 
  
  <div class="grid grid-cols-1 min-w-full">
    <ul class="overflow-auto" style="height: 90vh;">

        <div class="px-6">
          
          <div
            class="
              flex
              justify-between
              
              h-30
              p-4
              my-6
              rounded-lg
              border  border-gray-100
              shadow-md
            "
            v-for="login in user" :key="login.id"
          >
              <router-link :to="{ name : 'FriendProfile'}">
                <p class='py-2 px-4 border-gray-900 text-gray-900 hover:shadow-md rounded-md cursor-pointer'>
                  {{ login.login }}
                </p>
              </router-link>
            
            <div class=" flex gap-x-4">
              <button @click="func('Unfriend')" class='py-2 px-4 border-red-400 text-red-400 hover:shadow-lg rounded-md border'>Unfriend</button>
              <button @click="func('Block')" class='py-2 px-4 border-red-400 text-red-400 hover:shadow-lg rounded-md border'>Block</button>
              <button @click="func('Message')" class='py-2 px-4 border-blue-400 text-blue-400 hover:shadow-lg rounded-md border'>Message</button>
            </div>

          </div>
        </div>

    </ul>
  </div>
  </div>


</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Navbar from './Friends/Navbar.vue';

export default defineComponent({
    name: 'FriendsBlock',
    data()
    {
        return {
            login : "ayghazal",
            user : [{login: 'ayghazal', id : 1}, {login : "mohammed", id: 2}, {login: "hamza", id: 3}]
        }
    },
    methods : {
      func(arg : string)
      {
        console.log(arg);
      }

    },
    components : {
        Navbar,
    }
})
</script>