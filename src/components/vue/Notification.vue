<script setup>
  import {ref} from 'vue'

  let qty = ref(0)

  function add () {
    qty.value++
    console.log(qty)
  }

  function substract() {
    qty.value--
  }
</script>

<template>
  <div class="max-w-80 mx-auto p-6 bg-purple-300 rounded">
    <div 
      v-if="qty > 0"
      class="bg-red-500 text-white size-8 rounded-full flex justify-center items-center font-bold"
      :class="{'bg-orange-500': qty > 3 }"
    >
      {{ qty }}
    </div>
    <div v-else>
      Nadie te visita :(
    </div>
    <div 
      @click="add"
      class="bg-blue-400 text-white rounded size-6 flex justify-center items-center"
    >
      +
    </div>
    <div 
      @click="substract"
      class="bg-blue-400 text-white rounded size-6 flex justify-center items-center"
    >
      -
    </div>
  </div>
</template>