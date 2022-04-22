<template>
    <div>
        <Navbar />
<div class="h-full mt-5">
 
  <div class="border-b-2 block md:flex">

    <div class="w-full md:w-2/5 p-4 sm:p-6 lg:p-8 bg-white shadow-md">
        <div class="flex justify-between">
            <span class="text-xl font-semibold block"> {{ user.name }} </span>
        </div>

        <div class="w-full p-8  mx-2 flex justify-center">
            <img id="showImage" class="rounded-full max-w-xs w-32 items-center border" :src="user_avatar">
        </div>
        <div class="w-full p-8 mx-2 flex justify-around">
        <div  class=" rounded-lg font-bold text-white text-center px-4 py-3 transition duration-300 ease-in-out hover:bg-blue-600 mr-6 cursor-pointer"
        :class="addStyle"
        >
            {{msg_status}}
        </div>
        </div>
    </div>
    
    <div class="w-full md:w-3/5 p-8 bg-white lg:ml-4 shadow-md">
    <div class="grid grid-cols-1 min-w-full rounded">
                <ul class="overflow-auto hideScrollBar" style="height: 40vh;">
                    <li>
                        <div class="px-6"
                        v-for="players in user_history" :key="players.id"
                        >
                            <div class="flex justify-around items-center h-30 p-4 my-6  rounded-lg border border-gray-100 shadow-md">
                            <div class="flex items-center">
                                <div class="ml-2">
                                        <img id="showImage" class="rounded-full max-w-xs w-32 items-center border" :src="players.user1_avatar">
                                </div>
                            </div>
                            
                            <div class="flex items-center">
                                <div class="ml-2">
                                    {{players.user1_score}} - {{players.user2_score}}
                                </div>
                            </div>

                            <div class="flex items-center">
                                <div class="ml-5">
                                    <img id="showImage" class="rounded-full max-w-xs w-32 items-center border" :src="players.user2_avatar">
                                </div>
                            </div>
                            
                            <div>

                            </div>
                        </div>

                        </div>



                    </li>
                </ul>
    </div>

    </div>

  </div>
 
</div>

    </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue'
import Navbar from './Navbar.vue';


export default defineComponent({
  components: { Navbar },
    name: 'FriendProfile',
    data()
    {
        return {
            msg_status : "offline",
            msg : "friendProfile component Helloooo",
            user : {
                avatar_url: 'https://images.unsplash.com/photo-1503023345310-bd7c1de61c7d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MXx8aHVtYW58ZW58MHx8MHx8&w=1000&q=80' as string,
                name: 'user name' as string,
                status: 0 as number, // 0  offling 1 online 2 in game
            },
            user_history: [
                {
                    id: 0 as number,
                    user1_avatar: 'https://media.istockphoto.com/photos/rear-view-of-man-looking-at-city-in-sunlight-picture-id876576796?k=20&m=876576796&s=612x612&w=0&h=0IObpcqCk-i6atRIX8D0odOIVr7wIZfM6XgVosy67CI=' as string,
                    user2_avatar: 'https://media.istockphoto.com/photos/rear-view-of-man-looking-at-city-in-sunlight-picture-id876576796?k=20&m=876576796&s=612x612&w=0&h=0IObpcqCk-i6atRIX8D0odOIVr7wIZfM6XgVosy67CI=' as string,
                    user1_score: 1000 as number,
                    user2_score: 10 as number,
                },
                              {
                    id: 0 as number,
                    user1_avatar: 'https://media.istockphoto.com/photos/rear-view-of-man-looking-at-city-in-sunlight-picture-id876576796?k=20&m=876576796&s=612x612&w=0&h=0IObpcqCk-i6atRIX8D0odOIVr7wIZfM6XgVosy67CI=' as string,
                    user2_avatar: 'https://media.istockphoto.com/photos/rear-view-of-man-looking-at-city-in-sunlight-picture-id876576796?k=20&m=876576796&s=612x612&w=0&h=0IObpcqCk-i6atRIX8D0odOIVr7wIZfM6XgVosy67CI=' as string,
                    user1_score: 1000 as number,
                    user2_score: 10 as number,
                },
                              {
                    id: 0 as number,
                    user1_avatar: 'https://media.istockphoto.com/photos/rear-view-of-man-looking-at-city-in-sunlight-picture-id876576796?k=20&m=876576796&s=612x612&w=0&h=0IObpcqCk-i6atRIX8D0odOIVr7wIZfM6XgVosy67CI=' as string,
                    user2_avatar: 'https://media.istockphoto.com/photos/rear-view-of-man-looking-at-city-in-sunlight-picture-id876576796?k=20&m=876576796&s=612x612&w=0&h=0IObpcqCk-i6atRIX8D0odOIVr7wIZfM6XgVosy67CI=' as string,
                    user1_score: 1000 as number,
                    user2_score: 10 as number,
                },
                              {
                    id: 0 as number,
                    user1_avatar: 'https://media.istockphoto.com/photos/rear-view-of-man-looking-at-city-in-sunlight-picture-id876576796?k=20&m=876576796&s=612x612&w=0&h=0IObpcqCk-i6atRIX8D0odOIVr7wIZfM6XgVosy67CI=' as string,
                    user2_avatar: 'https://media.istockphoto.com/photos/rear-view-of-man-looking-at-city-in-sunlight-picture-id876576796?k=20&m=876576796&s=612x612&w=0&h=0IObpcqCk-i6atRIX8D0odOIVr7wIZfM6XgVosy67CI=' as string,
                    user1_score: 1000 as number,
                    user2_score: 10 as number,
                },
            ]  as Array<any>

        }
    },
    computed: {
        user_avatar () : string {
            return this.user.avatar_url;
        },
        addStyle() : string
        {
            if (this.user.status === 0)
                return 'bg-blue-500';
            else if (this.user.status === 1)
                return 'bg-green-500';          
            return 'bg-yellow-500';
        }
    },
    component : { // s
        Navbar,
    }

})
</script>

<style scoped>
.hideScrollBar::-webkit-scrollbar {
    display: none;
}

.hideScrollBar
{
    -ms-overflow-style: none;
  scrollbar-width: none;
}
</style>