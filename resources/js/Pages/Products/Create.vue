<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import TextInput from '@/Components/TextInput.vue';
import InputLabel from '@/Components/InputLabel.vue';
import { Link } from '@inertiajs/vue3';
import { inject } from 'vue';


const darkTheme = inject('darkTheme');
</script>

<template>
    <Head title="Products" />

    <AuthenticatedLayout>
        <div>
            <div class="m-10 flex justify-start">
                <Link :href="route('product')"
                class="bg-white p-2 ps-4 pe-4 shadow-lg rounded-lg">
                    <i class="fa fa-arrow-left"></i> Back
                </Link>
            </div>

            <div :class="{ 'filter invert': darkTheme }" class="flex justify-center">
                <div class="p-5 shadow-lg rounded-lg bg-white w-[1200px]">
                    <h1 class="flex justify-start"><b>Product Details</b></h1> <br>
                    <div class="flex">
                        <div class="w-[500px]">
                            <InputLabel for="product" value="Product name" />
                            <TextInput
                            type="text"
                            class="block w-full mt-1"
                            id="product" /> <br>

                            <InputLabel for="brand" value="Brand" />
                            <TextInput
                            type="text"
                            class="block w-full mt-1"
                            id="brand" /> <br>


                            <InputLabel for="retail_price" value="Retail Price" />
                            <TextInput
                            type="number"
                            class="block w-full mt-1"
                            id="retail_price" /> <br>

                            <InputLabel for="qty_stock" value="Quantity Stock" />
                            <TextInput
                            type="number"
                            class="block w-full mt-1"
                            id="qty_stock" /> <br>



                            <InputLabel for="brand" value="Category" />
                            <select id="brand" class="block w-full mt-1 border-gray-300 rounded-md shadow-sm focus:border-indigo-500 focus:ring-indigo-500">
                                <option value="" selected>-- Select a category --</option>
                            </select> <br>

                            <InputLabel for="description" value="Description" />
                            <textarea id="description" class="block w-full mt-1 border-gray-300 rounded-md shadow-sm focus:border-indigo-500 focus:ring-indigo-500"></textarea>
                            <br>
                            <button class="px-4 py-2 text-sm text-white bg-gray-500 rounded-md">Save</button>

                        </div>
                        <div class="ms-10">
                            <label for="dropzone-file">
                                <div class="w-[600px] h-[575px] bg-slate-300 flex items-center justify-center p-10 rounded-lg shadow-lg">
                                    <p class=""><span class="font-semibold">Click to upload a photo</span></p>
                                </div>
                                <input id="dropzone-file" type="file" class="hidden" />
                            </label>
                        </div>
                    </div>
                </div>
            </div>
        </div>


    </AuthenticatedLayout>
</template>
