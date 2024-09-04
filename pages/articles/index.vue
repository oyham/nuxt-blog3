<script setup>
const posts = await queryContent().find()
console.log(posts)
</script>

<template>
    <h1 class="text-3xls font-bold mb-10">Local Articles Page</h1>
    <section class="flex flex-wrap basis-4 gap-4 justify-center">
        <!-- Recuperamos el atículo por el atributo _path (nombre del archivo ej: /example) -->
        <article v-for="{ title, id, _path } in posts" :key="id" class="w-64 hover:animate-background rounded-xl bg-gradient-to-r from-green-300 via-blue-500 to-purple-600 p-0.5 shadow-xl transition hover:bg-[length:400%_400%] hover:shadow-sm hover:[animation-duration:_4s]">
            <div class="rounded-[10px] bg-white p-4 !pt-20 sm:p-6">
                <time datetime="2022-10-10" class="block text-xs text-gray-500"> 10th Oct 2022 </time>
                <!-- Quitamos la / luego de articles ya que _path devuelve /path -->
                <NuxtLink :to="`/articles${_path}`">
                <h3 class="mt-0.5 text-lg font-medium text-gray-900">
                    {{title}}
                </h3>
                </NuxtLink>
            </div>
        </article>
    </section>
</template>