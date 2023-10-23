<script setup>
import { defineProps, inject } from 'vue';

const props = defineProps({
  client: Object,
});

const darkTheme = inject('darkTheme');
</script>

<template>
    <div :class="{ ' text-black': !darkTheme, ' text-white': darkTheme }" >
        <div class="p-3 m-3 shadow-lg rounded-lg" :class="{ ' bg-gray-100': !darkTheme, ' bg-gray-700': darkTheme }">
            <h1 class="p-3 rounded-lg shadow-lg m-3" style="font-size: 30px;"><b>Name:</b> {{ client.first_name }} {{ client.last_name }}</h1>
            <h1>Address: {{ client.address }}</h1>
            <h1>Phone: {{ client.phone }}</h1>
            <h1>Credit Limit: {{ client.credit_limit }}</h1>
        </div>
    </div>
  </template>
