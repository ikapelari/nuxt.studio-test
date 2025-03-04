<script setup lang="ts">
const { data: page } = await useAsyncData(() => queryCollection('content').path('/test').first())


useSeoMeta({
    title: page.value?.title,
    description: page.value?.description
})
</script>

<template>
    <ContentRenderer v-if="page" :value="page" />
    <div v-else>Test not found</div>
</template>
