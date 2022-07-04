<script setup lang="ts">
type Article = {
    id?: number
    title: string
    body: string
}
const route = useRoute()
definePageMeta({
    layout: 'home',
})
const articleId = await route.params.id
const article: Article = await $fetch(`https://jsonplaceholder.typicode.com/posts/${articleId}`)
</script>

<template>
    <div class="flex gap-2">
        <aside class="hidden md:card  w-16 flex-none ">Left side</aside>
        <div class="bg-base-100 flex-auto">
            <!-- <div>{{ article.title }} </div>
            <aside>{{ article.body }} </aside> -->
            <TipTapEditor class="prose md:prose-2xl" :title="article.title" :body="article.body" />
        </div>
        <div class="hidden lg:card max-w flex-none">Right side</div>
    </div>
</template>
