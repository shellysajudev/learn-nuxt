<template>
    <div class="grid grid-cols-4 gap-4 mt-10">
        <nuxt-link to="/iphone/iphone-12" class="border rounded shadow-lg text-center">
            <h1>Iphone 12</h1>
            <div class="flex justify-center">
                <img width="200" src="/images/iphone-12.jpg" alt="">
            </div>
        </nuxt-link>
        <nuxt-link to="/iphone/iphone-12-pro" class="border rounded shadow-lg text-center">
            <h1>Iphone 12 Pro</h1>
            <div class="flex justify-center">
                <img width="200" src="/images/iphone-12-pro.jpg" alt="">
            </div>
        </nuxt-link>
    </div>
</template>

<script>
useHead({
    title: "Nuxt 3 Iphone"
})
</script>