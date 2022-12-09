<template>
    <div>        
        <button @click="moveToAbout">Take me to about</button>
        Hello Index
    </div>
</template>

<script setup>
function moveToAbout() {
    navigateTo('about');
}
</script>