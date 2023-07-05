<script setup>
    import {computed, onMounted} from 'vue'
    import store from '../store'
    import axiosClient from '../axiosClient'
    const letters='ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('');

    onMounted(() => {
        axiosClient.get('/list.php?i=list')
            .then(function(response){
                console.log(response);
            })

    })
</script>

<template>
    <div class="flex flex-col p-8 ">
        <div>
            <input type="text" name="" id="" placeholder="Search for meals" class="rounded border-grey-200 border-2 w-full"/>
        </div>

        <div class="flex justify-center gap-2 mt-2">
            <router-link :to="{name:'byLetter', params:{letter:letter}}" v-for="letter in letters" :key="letter">
                {{ letter }}
            </router-link>
        </div>
    </div>
    
</template>

<style>
  
</style>