<template>
    <div>
        <Navbar />
        <div v-if="$page.props.flash.message" class="alert bg-green-200 mt-4 mx-5 px-4 py-2">
            {{ $page.props.flash.message }}
        </div>

        <slot />
    </div>

</template>

<script setup>
import Navbar from '@/Components/Navbar.vue';
</script>
