<template>
    <nav class="font-mono">
        <ul class="flex space-x-4">
            <li>
                <NuxtLink to="/" class="text-blue-500">Main</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/about" class="text-blue-500">About</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/sohan" class="text-blue-500">Sohan</NuxtLink>
            </li>
        </ul>
    </nav>
</template>
<style scoped>
 .link{
    @apply p-1 hover:bg-gray-200
 }
</style>