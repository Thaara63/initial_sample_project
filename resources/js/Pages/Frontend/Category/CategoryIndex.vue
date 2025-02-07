<template>

    <Head title="Category page" />

    <FrontendLayout>
        <div class="mt-4 mx-4">
            <div class="flex justify-between">
                <h5>Category Lists</h5>
                <Link :href="route('categories.create')" class="bg-blue-500 text-white p-3 rounded mb-4">Add Category</Link>
            </div>
            <table class="w-full bg-white border border-gray-200 shadow">
                <thead>
                    <tr>
                        <th class="py-2 px-4 text-left border">Id</th>
                        <th class="py-2 px-4 text-left border">Category</th>
                        <th class="py-2 px-4 text-left border">Action</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td class="py-2 px-4 border">1</td>
                        <td class="py-2 px-4 border">Laptops</td>
                        <td class="py-2 px-4 border">
                            <Link
                                :href="route('categories.create')"
                                 class="px-2 py-1 text-sm bg-blue-300 text-dark me-2 rounded inline-block"
                            >
                                Show
                            </Link>
                            <Link
                                :href="route('categories.create')"
                                 class="px-2 py-1 text-sm bg-green-500 text-white me-2 rounded inline-block"
                            >
                                Edit
                            </Link>
                            <button
                                type="submit"
                                 class="px-2 py-1 text-sm bg-red-600 text-white me-2 rounded inline-block"
                            >
                                Delete
                            </button>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>


    </FrontendLayout>

</template>

<script setup>
import FrontendLayout from '@/Layouts/FrontendLayout.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

defineProps({
    categories: Array,
});


</script>
