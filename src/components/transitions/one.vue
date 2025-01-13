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

    <hr>
    <transition name="slide">
        <div class="p-3 mb-2 bg-success text-white" v-if="data.display3">
            Hello
        </div>

    </transition>
    <button class="btn btn-primary" @click="data.display3 = !data.display3">
        Toggle
    </button>

    <hr>
    <transition name="slideup">
        <div class="p-3 mb-2 bg-success text-white" v-if="data.display4">
            Hello
        </div>

    </transition>
    <button class="btn btn-primary" @click="data.display4 = !data.display4">
        Toggle dsiplay 4
    </button>
</template>

<script setup>
import { reactive } from 'vue';

const data = reactive({
    display: false,
    display2: true,
    display3: true,
    display4: true,
})
</script>

<style>
.slide-enter-from {
    transform: translateX(20px);
    opacity: 0;
}

.slide-leave-to {
    opacity: 0;
}

.slide-enter-active {
    transition: all 1s ease
}

.slide-enter-active {
    transition: all 1s ease
}


.slide-leave-active {
    transition: 2s;
}

.slide-enter-to {
    opacity: 1;
}

.slide-leave-from {
    opacity: 1;
    transform: translateX(20px);
    background-color: red;
}


.slideup-enter-active {

    animation: slideDown .5s ease-in-out;

}

.slideup-leave-active {
    animation: slideDown .5s ease-in-out;
}

@keyframes slideDown {
    from {
        opacity: 0;
        transform: translateY(10px);

    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}
</style>