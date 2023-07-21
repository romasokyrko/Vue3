<template>
    <transition name="header" appear>
        <div class="navbar">
        <div @click="$router.push('/')">Vue 3</div>
        <div class="navbar__btns">
            <my-button @click="$router.push('/posts')">Posts</my-button>
            <my-button style="margin-left: 20px;" @click="$router.push('/about')">About</my-button>
            <my-button style="margin-left: 20px;" @click="$router.push('/store')">Store</my-button>
            <my-button style="margin-left: 20px;" @click="$router.push('/composition')">Composition</my-button>
        </div>
    </div>
    </transition>
</template>

<script>
    export default {
    }
</script>

<style scoped>

    .header-enter-from, .header-leave-to {
        opacity: 0;
        transform: translateY(-10px);
    }
    .header-enter-to, .header-leave-from {
        opacity: 1;
        transform: translateY(0);
    }
    .header-enter-active, .header-leave-active {
        transition: all 1.0s ease-in;
    }
    .navbar {
        height: 50px;
        background-color: lightgray;
        box-shadow: 2px 2px 4px gray;
        display: flex;
        align-items: center;
        padding: 0 15px;
    }

    .navbar__btns {
          margin-left: auto;
    }
</style>