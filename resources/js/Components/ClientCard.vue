<script setup>
import { defineProps, inject } from 'vue';
import { router } from '@inertiajs/vue3';

const props = defineProps({
    client: Object,
});

const darkTheme = inject('darkTheme');

const viewClient = () => {
    router.get('/client/view/' + props.client.id);
};
</script>

<template>
    <div @click="viewClient" style="cursor: pointer;" class="h-[300px] w-[600px] m-10 p-3 shadow-lg rounded-lg">
        <div class="m-3 p-3 shadow-lg rounded-lg" :class="{ 'bg-gray-100': !darkTheme, 'bg-gray-700': darkTheme }">
            <h1 :class="{ 'text-gray-700': !darkTheme, 'text-gray-200': darkTheme }" style="font-size: 20px;"><b>Client Name:</b> {{ client.first_name }} {{ client.last_name }}</h1>
        </div>
        <br>
        <div :class="{ 'text-gray-700': !darkTheme, 'text-white': darkTheme }">
            <b>Address:</b> {{ client.address }} <br> <br>
            <b>Phone:</b> {{ client.phone }} <br> <br>
            <b>Credit Limit:</b> {{ client.credit_limit }} <br>
        </div>
    </div>
    <!-- <div class="min-w-[350px] mb-4 mx-2 p-4 bg-white rounded shadow border flex-1 cursor-pointer" @click="viewClient" :class="{ 'filter invert': darkTheme }">
        <h5 class="flex items-center mb-2 text-2xl font-bold tracking-tight" :class="darkTheme ? 'text-black' : 'text-gray-700'">
            {{ client.first_name }} {{ client.last_name }}
        </h5>
        <div class="mb-2">
            <p class="text-sm font-semibold" :class="darkTheme ? 'text-black' : 'text-gray-700'">Address</p>
            <p class="text-sm font-light" :class="darkTheme ? 'text-black' : 'text-gray-700'">{{ client.address }}</p>
        </div>
        <div class="mb-2">
            <p class="text-sm font-semibold" :class="darkTheme ? 'text-black' : 'text-gray-700'">Phone</p>
            <p class="text-sm font-light" :class="darkTheme ? 'text-black' : 'text-gray-700'">{{ client.phone }}</p>
        </div>
        <div>
            <p class="text-sm font-semibold" :class="darkTheme ? 'text-black' : 'text-gray-700'">Credit Limit</p>
            <p class="text-sm font-light" :class="darkTheme ? 'text-black' : 'text-gray-700'">{{ client.credit_limit }}</p>
        </div>
    </div> -->
</template>
