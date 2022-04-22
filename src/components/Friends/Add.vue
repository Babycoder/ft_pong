<template>

    <div>
    <Navbar />
    <h3 class="px-4 pt-8">Play with Friends it's more fun!</h3>

    <div>
    <form class="m-4 flex" @submit.prevent="submit">
        <input v-model="username"  id="user" class="rounded-l-lg p-4 border-t mr-0 border-b border-l text-gray-800 border-gray-200 bg-white" placeholder="Enter Login"/>
        <button class="px-8 rounded-r-lg bg-green-500  text-gray-800 font-bold p-4 uppercase border-white border-t border-b border-r">Send</button>
    </form>
    </div>

    <p class="px-4 pt-4 text-red-500">
        {{msg}}
    </p>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Navbar from "./Navbar.vue"

export default defineComponent({
    name: 'Add',
    data()
    {
        return {
            username: "" as string,
            msg : "" as string
        }
    },
    methods : {
        submit() {
            if (this.username.trim().length > 0)
            {
                // send username to Endpoint;
                console.log(this.username);
                this.msg = "";
            }
            else
            {
                this.msg = "Please Enter a Valid Input!!";
            }
 
            this.username = "";
        },

    },
    components : {
        Navbar,
    }
})
</script>