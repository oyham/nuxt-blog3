<script setup>
import { ref } from 'vue';

const posts = ref([])

//se puede realizar uso de await ya que la petición se realiza antes de que se renderice el componente
const res = await fetch('https://jsonplaceholder.typicode.com/posts')
//variable reactiva ? 
posts.value = await res.json()

</script>

<template>
    <h1 class="text-3xls font-bold mb-10">Posts</h1>
    <section>
        <div v-for="{ title, id } in posts" :key="id">
            {{title}}
        </div>
    </section>
</template>