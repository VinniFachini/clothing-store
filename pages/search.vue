<template>
    <Head>
    <Title>{{ route.query.query ? route.query.query : "Search Page" }} - Clothing Store Search</Title>
    <Meta name="description" content="{{ route.query.query ? route.query.query : 'Search Page' }}"/>
  </Head>
</template>

<script setup lang="ts">
const route = useRoute()
</script>