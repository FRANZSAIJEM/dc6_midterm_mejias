<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
import { ref, computed } from 'vue';
import ClientDetails from '@/Components/ClientDetails.vue'; // Import the ClientDetails component
import SalesTable from '@/Components/SalesTable.vue'; // Import the SalesTable component

const props = defineProps({
  client: Object,
  sales: Array,
});
</script>

<template>
    <AuthenticatedLayout>
      <div class="m-5 flex flex-wrap justify-center">
        <ClientDetails :client="client" />
        <SalesTable :sales="sales" />
      </div>
    </AuthenticatedLayout>
  </template>
