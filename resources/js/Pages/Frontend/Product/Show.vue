<template>
    <Head title="Show Product" />
    <FrontendLayout>

        <div class="mt-4 mx-4">
            <div class="flex justify-between">
                <h5>Show Product</h5>
                <Link :href="route('products.index')" class="bg-red-600 text-white py-2 px-5 inline-block rounded mb-4">Back</Link>
            </div>

                <div class="grid grid-cols-6 gap-4">
                    <div class="col-span-6">
                        <div class="mb-3">
                            <label>Product Name</label>
                            <p>
                                {{ product.name }}
                            </p>
                        </div>
                        <div class="mb-3">
                            <label>Product Price</label>
                            <p>
                                {{ product.price }}
                            </p>
                        </div>
                        <div class="mb-3">
                            <label>Product Description</label>
                            <p>
                                {{ product.description }}
                            </p>
                        </div>
                        <div class="mb-3">
                            <label>Product Category</label>
                            <p>
                                {{ product.category.category_name }}
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

defineProps({
    errors : Object,
    product : Object,
    categories : Array,
});
</script>
