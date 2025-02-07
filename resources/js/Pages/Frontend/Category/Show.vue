<template>
    <Head title="Show Category" />
        <FrontendLayout>

            <div class="mt-4 mx-4">
                <div class="flex justify-between">
                    <h5>Show Category</h5>
                    <Link :href="route('categories.index')" class="bg-red-600 text-white py-2 px-5 inline-block rounded mb-4">Back</Link>
                </div>

                    <div class="grid grid-cols-6 gap-4">
                        <div class="col-span-6">
                            <div class="mb-3">
                                <label>Category Name</label>
                                <p>
                                    {{ category.category_name }}
                                </p>
                            </div>
                        </div>
                    </div>

            </div>


        </FrontendLayout>
    </template>

    <script setup>
    import FrontendLayout from '@/Layouts/FrontendLayout.vue';
    import { Head, Link } from '@inertiajs/vue3';

    const props = defineProps({
        errors : Object,
        category : Object,
    });
    </script>
