<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" />
  </div>
</template>

<script>
import PostForm from '@/components/PostForm.vue';
import PostList from '@/components/PostList.vue';

export default {
  components: {
    PostForm,
    PostList,
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
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
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
