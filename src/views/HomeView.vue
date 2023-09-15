<template>
  <div>
    <h1>Home</h1>
    <div v-if="error">{{ error }}</div>
    <PostList v-if="posts.length" :posts="posts"/>
    <div v-else>loading...</div>
  </div>
</template>

<script>
import PostList from '@/components/PostList.vue';
import getPosts from '../composables/getPosts'


export default {
    name: 'HomeView',
    setup() {
      const { posts, error, load} = getPosts()
      
      load()
      
      return {posts, error}
    },
    components: { PostList }
}
</script>
