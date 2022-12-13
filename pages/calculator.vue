<template>
    <section>
        <div>
            <h1 class="text-3xl">Calculator</h1>
        </div>
        <div class="w-48">
            <p class="text-3xl text-right my-2">{{ (currentNum=='') ? '0' : currentNum }}</p>
            <small v-if="selectedOperation">{{ prevNum }} {{ selectedOperation }} {{ currentNum }}</small>
            <div class="grid grid-cols-4 gap-2">
                <button @click="pressed('1')" class="p-2 w-10 h-10 border rounded shadow">1</button>
                <button @click="pressed('2')" class="p-2 w-10 h-10 border rounded shadow">2</button>
                <button @click="pressed('3')" class="p-2 w-10 h-10 border rounded shadow">3</button>
                <button @click="pressed('+')" class="p-2 w-10 h-10 border rounded shadow">+</button>
                <button @click="pressed('4')" class="p-2 w-10 h-10 border rounded shadow">4</button>
                <button @click="pressed('5')" class="p-2 w-10 h-10 border rounded shadow">5</button>
                <button @click="pressed('6')" class="p-2 w-10 h-10 border rounded shadow">6</button>
                <button @click="pressed('-')" class="p-2 w-10 h-10 border rounded shadow">-</button>
                <button @click="pressed('7')" class="p-2 w-10 h-10 border rounded shadow">7</button>
                <button @click="pressed('8')" class="p-2 w-10 h-10 border rounded shadow">8</button>
                <button @click="pressed('9')" class="p-2 w-10 h-10 border rounded shadow">9</button>
                <button @click="pressed('/')" class="p-2 w-10 h-10 border rounded shadow">/</button>
                <button @click="pressed('C')" class="p-2  w-10 h-10 border rounded shadow">C</button>
                <button @click="pressed('0')" class="p-2  w-10 h-10 border rounded shadow">0</button>
                <button @click="pressed('=')" class="p-2 w-10 h-10 border rounded shadow">=</button>
                <button @click="pressed('*')" class="p-2 w-10 h-10 border rounded shadow">*</button>
            </div>
        </div>
    </section>
</template>

<script setup>
const prevNum = ref('');
const currentNum = ref('');
const selectedOperation = ref('');
const operations = ['+','-','/','*'];
const numbers = ['0','1','2','3','4','5','6','7','8','9'];
function pressed(value) {
    if(value == '=' || value == 'Enter'){
        calculate();
    }else if(value=='C' || value=='c'){
        clear();
    }else if(operations.includes(value)){
        applyOperation(value);
    }else if(numbers.includes(value)){
        appendNumber(value);        
    }
}
function appendNumber(value) {
    currentNum.value = currentNum.value + value;
}
function applyOperation(value) {
    calculate();
    prevNum.value = currentNum.value;
    currentNum.value = '';
    selectedOperation.value = value;
}
function calculate() {
    switch (selectedOperation.value) {
        case '+':
            currentNum.value = +prevNum.value + +currentNum.value;
            break;
        case '-':
            currentNum.value = prevNum.value - currentNum.value;
            break;
        case '/':
            currentNum.value = prevNum.value / currentNum.value;
            break;
        case '*':
            currentNum.value = prevNum.value * currentNum.value;
            break;
    
        default:
            break;
    }
    prevNum.value = '';
    selectedOperation.value = '';
}
function clear() {
    currentNum.value = '';
}

function handleKeydown(e) {
    pressed(e.key);
}

onMounted(()=>{
    window.addEventListener('keydown', handleKeydown)
})

onUnmounted(() => {
    window.removeEventListener('keydown', handleKeydown);
})
</script>