<template>
    <div>
        <button class="btn btn-primary" @click="status = !status">
            Toggle Status
        </button>
    </div>

    <transition mode="in-out" name="custom" enter-active-class="dog" leave-active-class="cat">
        <div class="p-3 mb-2 bg-danger text-white" v-if="!status" key="status_off">
            OFF
        </div>
        <div class="p-3 mb-2 bg-success text-white" v-else key="status_on">
            ON
        </div>
    </transition>
</template>

<script setup>
import { reactive, ref } from 'vue';


const status = ref(false);

</script>

<style>
.custom-enter-from {
    transform: translateX(20px);
    opacity: 0;
}

.slide-leave-to {
    opacity: 0;
}

.slide-enter-active {
    transition: all 1s ease
}

.dog,
.cat {
    transition: 2s;
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