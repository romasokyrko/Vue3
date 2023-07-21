<template>
    <navbar></navbar>
    <div class="app">

    <router-view v-slot="{Component}">
        <transition name="page" mode="out-in">
            <component :is="Component"></component>
        </transition>
    </router-view>
    </div>
</template>

<script>
import Navbar from '@/components/Navbar'
    export default {
  components: { Navbar },

    }
</script>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.app{
    padding: 20px;
}
.page-leave-to {
    opacity: 0;
    transform: translateX(-50px);
}
.page-leave-active {
    transition: all 0.4s ease-in;
}
.page-enter-from {
    opacity: 0;
    transform: translateX(50px);
}
.page-enter-active {
    transition: all 0.4s ease-out;
}
</style>