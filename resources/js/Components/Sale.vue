<script setup>
import { defineProps, inject } from 'vue';

const props = defineProps({
    sales: Array, // Ensure that this type matches the type of your sales prop
});

const darkTheme = inject('darkTheme');
</script>

<template>
    <div :class="darkTheme ? 'text-white' : 'text-gray-700'" class="h-[250px] w-[600px] m-10 p-3 shadow-lg rounded-lg" v-for="sale in sales" :key="sale.id">
        <div class="m-3 p-3 shadow-lg rounded-lg" :class="darkTheme ? 'bg-gray-700' : 'bg-gray-100'">
            <h1 style="font-size: 20px;"><b>Client Name: </b>{{ sale.client.first_name }} {{ sale.client.last_name }}</h1>
        </div> <br> <br>
        <h1><b>Date:</b> {{ sale.date }}</h1> <br>
        <h1><b>Is Credit:</b> {{ sale.is_credit ? 'Yes' : 'No'  }}</h1>
    </div>


    <!-- <div :class="darkTheme ? 'text-white' : 'text-gray-700'" class="mx-auto max-w-7xl sm:px-6 lg:px-8">
      <div :class="darkTheme ? 'bg-black' : 'bg-white'" class="overflow-hidden shadow-sm sm:rounded-lg">
        <div :class="darkTheme ? 'text-white' : 'text-gray-700'" class="p-6 text-gray-900">

          <table class="min-w-full divide-y divide-gray-200">
            <thead>
              <tr>
                <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50 dark:bg-gray-800 dark:text-gray-400">
                  Date
                </th>
                <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50 dark:bg-gray-800 dark:text-gray-400">
                  Client ID
                </th>
                <th class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase bg-gray-50 dark:bg-gray-800 dark:text-gray-400">
                  Is Credit
                </th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="sale in sales" :key="sale.id">
                <td class="px-6 py-4 whitespace-no-wrap">
                  {{ sale.date }}
                </td>
                <td class="px-6 py-4 whitespace-no-wrap">
                  {{ sale.client_id }}
                </td>
                <td class="px-6 py-4 whitespace-no-wrap">
                  {{ sale.is_credit ? 'Yes' : 'No' }}
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div> -->
  </template>
