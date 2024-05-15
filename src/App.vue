<template>
  <div>
    <div class="post" v-for="post in posts" :key="post.id">
      <div><strong>Название:</strong> {{ post.title }}</div>
      <div><strong>Описание:</strong> {{ post.description }}</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
      dislikes: 0,
      posts: [
        {id: 1, title: 'Пост о Vue', description: 'Прогрессивный JavaScript-фреймворк'},
        {id: 2, title: 'Пост о React', description: 'Почти JavaScript-фреймворк'},
        {id: 3, title: 'Пост о Angular', description: 'Фреймворк от Google'}
      ]
    }
  },
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislikes += 1;
    }
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .post {
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
  }
</style>