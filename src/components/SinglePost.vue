<template >
    <div>
        <h3>{{ post.title }}</h3>
        <p v-html="snipped"></p>
    </div>
</template>
<script>
import { computed } from 'vue';

export default {
    props:['post'],
    setup(props) {
        const snipped = computed(() => {
            return props.post.body.substring(0,100) + '...'
        })
        return {snipped}
    }
}
</script>
<style lang="">
    
</style>