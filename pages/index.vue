
<script setup  lang="ts">
definePageMeta({
    layout: 'home',
})
// console.log(await $fetch('https://jsonplaceholder.typicode.com/posts'))
const posts = await $fetch('https://jsonplaceholder.typicode.com/posts')
</script>

<template>
    <div>
        <div class="hero  bg-base-100">
            <div class="hero-content text-center">
                <div class="max-w-md">
                    <h1 class="text-5xl font-bold">Hello there</h1>
                    <p class="py-6">
                        HERO cupiditate voluptatem et in. Quaerat fugiat ut assumenda excepturi exercitationem
                        quasi. In deleniti eaque aut repudiandae et a id nisi.
                    </p>
                    <button class="btn btn-primary">Get Started</button>
                </div>
            </div>
        </div>
        <br />
        <div class="grid grid-cols-4 gap-4 ">
            <LeftSidebar />
            <div class="col-span-4 md:col-span-3 lg:col-span-2">
                <div class="flex flex-col">
                    <ul>
                        <li class="mb-2" v-for="article in posts">
                            <Card :title="article.title" :firstSentence="article.body" :id="article.id"
                                img-src="https://api.lorem.space/image/game?w=800&h=300" />
                        </li>
                    </ul>
                </div>
            </div>
            <div class="hidden lg:card max-w ">
                <div class="flex flex-col justify-start p-2">
                    <div class="card bg-base-200 my-1">1</div>
                    <div class="card bg-base-200 my-1">2</div>
                    <div class="card bg-base-200 my-1">3</div>
                </div>
            </div>
        </div>
    </div>
</template>
