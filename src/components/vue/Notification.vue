<script setup>

 import {ref} from "vue";
 
 let qty = ref(0);

 function add() {
    qty.value++
    console.log(qty)
 }

 function rest() {
    
    console.log(qty)
    if(qty.value>0){
        qty.value--    
    }else{
        qty.value='para we'
    }
 }
 

</script>
 
<template>
    <div class="bg-purple-950 rounded max-w-80 mx-auto p-6">
        <div
        v-if="qty>0" 
        :class="{'bg-gradient-to-r from-slate-700 to-red-600': qty==3}"
        class="bg-red-600 text-white size-8 rounded-full justify-center items-center font-bold inline-flex">
            {{ qty }}
        </div>
        <div v-else class="bg-red-600 text-white rounded-full justify-center items-center font-bold">
            Nadie te visita
        </div>

        <div 
        @click="add"
        class="bg-blue-400 text-white rounded size-6 inline-flex justify-center items-center hover:cursor-pointer mx-10">
        +
        </div>
        
        <div 
        @click="rest"
        class="bg-green-400 text-white rounded size-6 inline-flex justify-center items-center hover:cursor-pointer">
        -
        </div>


    </div>
</template>