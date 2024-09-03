<script setup>
// SPA TIMELINE: se renderiza al app sin la data
/* import { ref } from 'vue';

const posts = ref([])

//se puede realizar uso de await ya que la petición se realiza antes de que se renderice el componente
const res = await fetch('https://jsonplaceholder.typicode.com/posts')
//variable reactiva ? 
posts.value = await res.json() */


//SSR TIMELINE: se renderiza la app con la data
// Destructuring de data para llamarse post, haciendo uso de useFetch (no es necesario importarlo)
const {data: posts} = await useFetch('https://jsonplaceholder.typicode.com/posts')


</script>

<template>
    <h1 class="text-3xls font-bold mb-10">Posts</h1>
    <section class="flex flex-wrap basis-4 gap-4 justify-center">
        <article v-for="{ title, id } in posts" :key="id" class="w-64 hover:animate-background rounded-xl bg-gradient-to-r from-green-300 via-blue-500 to-purple-600 p-0.5 shadow-xl transition hover:bg-[length:400%_400%] hover:shadow-sm hover:[animation-duration:_4s]">
            <div class="rounded-[10px] bg-white p-4 !pt-20 sm:p-6">
                <time datetime="2022-10-10" class="block text-xs text-gray-500"> 10th Oct 2022 </time>
                <a href="#">
                <h3 class="mt-0.5 text-lg font-medium text-gray-900">
                    {{title}}
                </h3>
                </a>
            </div>
        </article>
    </section>
</template>