<!-- original name [slug].vue -->
<template>
    <!-- Hacemos uso de un componente del módulo Content -->

    <!-- Si los contenidos .md se encontrarían en la misma ruta de articles, no haría falta utilizar ContentDoc -->

    <!-- Renderiza el body por todo lo que tenga el .md -->
    <ContentDoc :path="`${$route.params.path}`">
        <template #not-found>
            <h1>Article not found</h1>
        </template>
    </ContentDoc>
</template>