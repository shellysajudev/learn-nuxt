<template>
    <div>
        <h1 class="text-3xl">Heros - {{ herosCount }}</h1>
        <div class="w-96 mt-5 rounded border shadow-lg p-5">
            <div class="flex justify-between" v-for="(hero,index) in dcHeros" :key="index">
                <h3>{{ index }}-{{ hero.name }}</h3>
                <span @click="remove(index)">x</span>
            </div>
            <div class="flex justify-between mt-5 gap-2">
                <input
                    type="text" 
                    v-model="newHero" 
                    class="border w-60 px-2" 
                    placeholder="Add Hero"
                    ref="newHeroRef"
                />
                <button class="border bg-green-700 text-gray-200 p-2 rounded-md hover:bg-opacity-80" @click="addHero">Add Hero</button>
            </div>
        </div>
    </div>
</template>

<script setup>
const newHero = ref('');
const newHeroRef = ref('');
const dcHeros = ref([
    { name: 'Supergirl' },
    { name: 'Flash' },
    { name: 'Batman' },
    { name: 'Arrow' },
    { name: 'Superman' },
]);

function remove(index) {
    dcHeros.value = dcHeros.value.filter((hero,i) => i != index);
};

function addHero() {
    if(newHero != ''){
        dcHeros.value.unshift({ name: newHero.value });
        newHero.value = '';
    }
}

onMounted(()=>{
    newHeroRef.value.focus();
});

const herosCount = computed({
    get: () => dcHeros.value.length,
});
</script>