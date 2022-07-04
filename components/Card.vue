<script setup lang="ts">
const props = defineProps({
    id: Number,
    title: String,
    firstSentence: String,
    imgSrc: String
})
const truncated = computed(() => { return props.firstSentence.length > 100 ? `${props.firstSentence.substring(0, 100)}...` : props.firstSentence })
</script>

<template>
    <div class="card bg-base-100 shadow-md">
        <figure><img :src="props.imgSrc" alt="Shoes" /></figure>
        <div class="card-body">
            <NuxtLink :to="`/article/${id}`" class="card-title">
                {{ title }}
                <div class="badge badge-secondary">NEW</div>
            </NuxtLink>
            <p>{{ truncated }}</p>
            <div class="card-actions justify-end">
                <div class="badge badge-outline">Fashion</div>
                <div class="badge badge-outline">Products</div>
            </div>
        </div>
    </div>
</template>
