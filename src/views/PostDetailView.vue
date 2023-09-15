<template>
    <div class="error" v-if="error">{{ error }}</div>
    <div v-if="post" class="post">
        <h3>{{ post.title }}</h3>
        <div class="pre" v-html="post.body"></div>
    </div>
    <div v-else>loading...</div>
</template>
<script>
import getPost from '@/composables/getPost';

export default {
    props:['id'],
    setup(props) {
        const { post, error, load } = getPost(props.id)
      
        load()
      
      return {post, error}
    }
}
</script>
<style>
    .post{
        max-width: 1200px;
        margin: 0 auto;
        padding:15px ;
    }
    .post p{
        color: #444;
        line-height: 1.5em;
        margin-top: 30px;
    }
    .post .pre{
        white-space: pre-wrap;
        text-align: left;
    }
    .post .pre li{
        margin-top: 10px;
    }
</style>