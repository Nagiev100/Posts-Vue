<template>
    <div class="App">
        <PostForm @create="createPost"/>
        <PostList :posts="posts"/>
    </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue";
import PostList from "@/components/PostList.vue";

export default {
    components: {
        PostForm, PostList
    },
    data() {
        return {
            posts: [
                {id: 1, title: "пост о JavaScript", body: "Крутой язык"},
                {id: 2, title: "пост о Payton", body: "Пойдет"},
                {id: 3, title: "пост о c#", body: "Норм"},
            ],
        }
    },
    methods: {
        createPost(post) {
            if (post.title === "" || post.body === "") return;
            this.posts.push(post)
        },
    }
}
</script>

<style> // scoped - флаг указывает что стили будут доступны только в этом компоненте
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.App {
    max-width: 500px;
    margin: 0 auto;
    padding: 20px;
}
</style>