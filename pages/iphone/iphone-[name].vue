<template>
    <p>Iphone {{ name }}</p>
</template>

<script>
// const route = useRoute();
// console.log(route);
// useHead({
//     title: `Nuxt3 - Iphone ${route.params.name}`
// })
export default{
    computed: {
        name(){
            console.log(this.$route.fullPath); 
            return 'test  ';
            // return this.$route.params.name.replaceAll('-',' ');
        }        
    }
}
</script>