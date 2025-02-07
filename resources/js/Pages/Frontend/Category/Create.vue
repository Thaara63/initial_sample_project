<template>
    <Head title="Create Category" />
    <FrontendLayout>

        <div class="mt-4 mx-4">
            <div class="flex justify-between">
                <h5>Create Category</h5>
                <Link :href="route('categories.index')" class="bg-red-600 text-white py-2 px-5 inline-block rounded mb-4">Back</Link>
            </div>

            <form @submit.prevent="saveCategory()">
                <div class="grid grid-cols-6 gap-4">
                    <div class="col-span-6">
                        <div class="mb-3">
                            <label>Category Name</label>
                            <input type="text" v-model="form.name" class="py-1 w-full" />
                            <div v-if="errors.name" class="text-red-500">{{ errors.name }}</div>
                        </div>
                        <div class="mb-3">
                            <Link
                                :href="route('categories.index')"
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
    errors:Object
});

const form = useForm({
    name:'',
});

const saveCategory = () => {
    const res = form.post(route('categories.store'));
    if(res){
        form.reset();
    }
};

</script>
