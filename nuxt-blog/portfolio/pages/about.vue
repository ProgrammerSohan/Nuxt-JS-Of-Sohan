<template>
    <div>
       <h1> This page is about me.</h1>
       <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. At dicta, quis temporibus excepturi mollitia ipsum vitae tenetur fuga? Aperiam voluptates dolores aspernatur veritatis voluptatibus debitis magni, ullam eveniet! Enim, explicabo?</p>
    </div>
    <div>
        <button @click="enableCustomLayout" class="text-orange-500">Update Layout</button>
    </div>
</template>
<script setup>
/*
definePageMeta({
    layout: 'another',
});*/
function enableCustomLayout(){
    setPageLayout('another')
}
</script>