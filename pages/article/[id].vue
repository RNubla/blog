<script setup>
const route = useRoute()
definePageMeta({
    layout: 'home',
})
const articleId = await route.params.id
const article = await $fetch(`https://jsonplaceholder.typicode.com/posts/${articleId}`)
console.log(article)
</script>
<template>
    <div>
        <div>{{ article.title }} </div>
        <div>{{ article.body }} </div>
    </div>
</template>
