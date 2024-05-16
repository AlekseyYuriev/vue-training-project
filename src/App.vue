<template>
  <div class="app">
    <h1>Страница с постами</h1>
    <my-button @click="showDialog" style="margin: 15px 0"
      >Создать пост</my-button
    >
    <my-dialog v-model:show="dialogVisible">
      <post-form @create="createPost" />
    </my-dialog>
    <post-list :posts="posts" @remove="removePost" />
  </div>
</template>

<script>
import PostForm from '@/components/PostForm.vue';
import PostList from '@/components/PostList.vue';
import MyDialog from './components/UI/MyDialog.vue';

export default {
  components: {
    PostForm,
    PostList,
    MyDialog,
  },
  data() {
    return {
      likes: 0,
      dislikes: 0,
      posts: [
        {
          id: 1,
          title: 'Пост о Vue',
          body: 'Прогрессивный JavaScript-фреймворк',
        },
        { id: 2, title: 'Пост о React', body: 'Почти JavaScript-фреймворк' },
        { id: 3, title: 'Пост о Angular', body: 'Фреймворк от Google' },
      ],
      dialogVisible: false,
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p !== post);
    },
    showDialog() {
      this.dialogVisible = true;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>
