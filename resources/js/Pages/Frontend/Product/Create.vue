<template>
    <Head title="Create Product" />
    <FrontendLayout>

        <div class="mt-4 mx-4">
            <div class="flex justify-between">
                <h5>Create Product</h5>
                <Link :href="route('products.index')" class="bg-red-600 text-white py-2 px-5 inline-block rounded mb-4">Back</Link>
            </div>

            <form @submit.prevent="saveProduct()">
                <div class="grid grid-cols-6 gap-4">
                    <div class="col-span-6">
                        <div class="mb-3">
                            <label>Product Name</label>
                            <input type="text" v-model="form.name" class="py-1 w-full" />
                            <div v-if="errors.name" class="text-red-500">{{ errors.name }}</div>
                        </div>
                        <div class="mb-3">
                            <label>Product Price</label>
                            <input type="text" v-model="form.price" class="py-1 w-full" />
                            <div v-if="errors.price" class="text-red-500">{{ errors.price }}</div>
                        </div>
                        <div class="mb-3">
                            <label>Description</label>
                            <input type="text" v-model="form.description" class="py-1 w-full" />
                            <div v-if="errors.description" class="text-red-500">{{ errors.description }}</div>
                        </div>
                        <div class="mb-3">
                            <label>Category</label>
                            <select v-model="form.category_id">
                                <option value="">Select Category</option>
                                <option v-for="category in categories"
                                    :key="category.id"
                                    :value="category.id"
                                >
                                    {{category.category_name}}
                                </option>
                            </select>
                            <div v-if="errors.category_id" class="text-red-500">{{ errors.category_id }}</div>
                        </div>
                        <div class="mb-3">
                            <Link
                                :href="route('products.index')"
                                class="bg-red-600 text-white py-2 px-5 rounded mb-4 inline-block"
                            >
                                Back
                            </Link>
                            <button
                                type="submit"
                                :disabled="form.processing"
                                class="bg-blue-500 text-white py-2 px-5 rounded mb-4"
                            >
                            <span v-if="form.processing">Saving...</span>
                            <span v-else>Save</span>
                            </button>

                        </div>
                    </div>
                </div>
            </form>

        </div>


    </FrontendLayout>
</template>

<script setup>
import FrontendLayout from '@/Layouts/FrontendLayout.vue';
import { Head, Link, useForm } from '@inertiajs/vue3';

defineProps({
    errors:Object,
    categories:Array,
});

const form = useForm({
    name:'',
    price:'',
    description:'',
    category_id:'',
});

const saveProduct = () => {
    const res = form.post(route('products.store'));
    if(res){
        form.reset();
    }
};
</script>
