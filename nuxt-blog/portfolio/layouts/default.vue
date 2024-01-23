<template>
    <div>
        <nav>
            <ul>
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
        <slot />
    </div>
</template>