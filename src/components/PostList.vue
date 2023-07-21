<template>
    <transition name="swap" mode="out-in">
        <div v-if="posts.length > 0">
        <h3>Posts List</h3>
        <transition-group name="user-list" tag="ul" appear>
            <post-item
            v-for="post in posts"
            :post="post"
            :key="post.id"
            @remove="$emit('remove', post)"
         />
        </transition-group>
    </div>
    <h2 v-else style="color: red;">Empty Posts</h2>
    </transition>
</template>

<script>
    import PostItem from "@/components/PostItem";

    export default {
        components: {PostItem},
        props: {
            posts: {
                type: Array,
                required: true
            }
        }
    }
</script>

<style scoped>
.swap-enter-from,
.swap-leave-to {
    opacity: 0;
    transform: translateY(10px);
}

.swap-enter-to,
.swap-leave-from {
    opacity: 1;
    transform: translateY(0);
}

.swap-enter-active,
.swap-leave-active {
    transition: all 0.5s ease;
}

.user-list-enter-to,
.user-list-leave-from {
  opacity: 1;
  transform: scale(1);
}
.user-list-enter-active {
    transition: all 0.5s ease;
}
.user-list-leave-active {
  transition: all 0.5s ease;
  position: absolute;
}
.user-list-enter-from,
.user-list-leave-to {
  opacity: 0;
  transform: scale(0.5);
}
.user-list-move {
    transition: all 0.5s ease;
}
</style>