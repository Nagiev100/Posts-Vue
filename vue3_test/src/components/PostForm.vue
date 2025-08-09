<template>
    <form @submit.prevent class="Form">
        <h4>Создание поста</h4>
        <input
                v-model="post.title"
                class="Input"
                type="text"
                placeholder="Название"
        />
        <input
                v-model="post.body"
                class="Input"
                type="text"
                placeholder="Описание"
        />
        <button @click="createPost" class="Btn">Создать</button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                id: null,
                title: "",
                body: ""
            }
        }
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit("create", this.post)
            this.post = {
                title: "",
                body: ""
            }
        }
    }
}
</script>

<style scoped>
.Form {
    display: flex;
    flex-direction: column;
}

.Input {
    max-width: 500px;
    border: 2px solid teal;
    padding: 10px 15px;
    margin-top: 15px;
}

.Btn {
    margin-top: 15px;
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    color: teal;
    border: 1px solid teal;
}

.Btn:hover {
    background-color: teal;
    color: white;
}
</style>