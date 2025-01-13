<template>
    <transition>
        <div class="p-3 mb-2 bg-success text-white" v-if="data.display">
            Hello
        </div>

    </transition>
    <button class="btn btn-primary" @click="data.display = !data.display">
        Toggle
    </button>

    <hr>
    <transition>
        <div class="p-3 mb-2 bg-success text-white" v-if="data.display2">
            Hello
        </div>

    </transition>
    <button class="btn btn-primary" @click="data.display2 = !data.display2">
        Toggle
    </button>
</template>

<script setup>
import { reactive } from 'vue';

const data = reactive({
    display: false,
    display2: true,
})
</script>

<style>
.v-enter-from,
.v-leave-to {
    opacity: 0;
}

.v-enter-active,
.v-leave-active {
    transition: 5s;
}

.v-enter-to,
.v-leave-from {
    opacity: 1;
}
</style>