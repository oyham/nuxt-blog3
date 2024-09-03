<script setup>
// Composable de useRoute dónde se guardan todas las rutas 
const route = useRoute()

const {data: post} = await useFetch(`https://jsonplaceholder.typicode.com/posts/${route.params.id}`)
</script>

<template>
    <!-- $route (palabra reservada) de nuxt para uso en template -->
    <!-- <h1>Detail page id:{{ $route.params.id }}</h1> -->
    <h1 class="text-3xl">{{post.title}}</h1>
    <p class="m-4">{{post.body}}</p>
</template>