<template>
    <div>
        <nav class="bg-gray-700 text-gray-800 shadow-lg flex gap-10 text-lg p-4">
            <NuxtLink to="/" class="bg-gray-100 shadow-lg py-1 px-4">Home</NuxtLink>
            <NuxtLink to="/about" class="bg-gray-100 shadow-lg py-1 px-4">About</NuxtLink>
            <NuxtLink to="/iphone" class="bg-gray-100 shadow-lg py-1 px-4">Iphones</NuxtLink>
            <NuxtLink to="/calculator" class="bg-gray-100 shadow-lg py-1 px-4">Calculator</NuxtLink>
            <NuxtLink to="/sample" class="bg-gray-100 shadow-lg py-1 px-4">Sample</NuxtLink>
            <NuxtLink to="/profile" class="bg-gray-100 shadow-lg py-1 px-4">Profile</NuxtLink>
        </nav>
        <main class="mx-40 mt-10">
            <slot></slot>
        </main>
    </div>
</template>