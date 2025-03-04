<script setup lang="ts">
const { data: test } = await useAsyncData(() => queryCollection('content').path('/').first())

useSeoMeta({
    title: test.value?.title,
    description: test.value?.description
})
</script>

<template>
    <ContentRenderer v-if="test" :value="test" />
    <div v-else>Test not found</div>
</template>
