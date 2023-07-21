<template>
    <transition name="createForm" appear>
        <form @submit.prevent>
            <h4>Create post</h4>
            <my-input
                v-focus
                v-model="post.title"
                type="text"
                placeholder="Name"
            />
            <my-input
                v-model="post.body"
                type="text"
                placeholder="Text"
            />
            <my-button
                style="align-self: flex-end; margin-top: 15px;"
                @click="createPost"
                >
                Create
            </my-button>
        </form>
    </transition>
</template>

<script>
    export default {
        data() {
            return {
                post: {
                    title: '',
                    body: ''
                }
            }
        },
        methods: {
            createPost() {
                this.post.id = Date.now();
                this.$emit('create', this.post)
                this.post = {
                    title: '',
                    body: ''
                }
            }
        },
    }
</script>

<style scoped>
 .createForm-enter-from, .createForm-leave-to {
        opacity: 0;
        transform: translateX(-80px);
    }
    .createForm-enter-to, .createForm-leave-from {
        opacity: 1;
        transform: translateY(0);
    }
    .createForm-enter-active, .createForm-leave-active {
        transition: all 0.5s ease;
    }

    form {
        display: flex;
        flex-direction: column;
    }
</style>