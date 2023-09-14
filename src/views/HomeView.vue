<template>
  <div>
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>search term: {{ search }}</p>
    <div v-for="name in matchingNames" :key="name">
      {{ name }}
    </div>

  </div>
</template>

<script>
import { computed, ref } from 'vue'


export default {
  
  name: 'HomeView',
  
  setup() {
    
    const search = ref('')
    const names = ref(['María', 'Carlos', 'Laura', 'Juan', 'Sofía', 'Pedro', 'Ana', 'Diego', 'Marta', 'Alejandro'])
    
    const matchingNames = computed(()=>{
      return names.value.filter((name)=>  name.includes(search.value))
    })
    return { names ,search,matchingNames}
  }
}
</script>
