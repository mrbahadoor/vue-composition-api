<template>
  <div>
    <button @click="increment">Center</button>
    <div>{{ counter }}</div>
    <div>{{ arrayOfEmojis }}</div>
  </div>
</template>
<script>
  import { ref, onMounted, watch, computed } from 'vue'

  export default {
    props: {
      emoji: {type: String, default: '🔥' }
    },
    setup(props) {
       console.log(props.emoji);

       onMounted(() => {
        console.log('Counter component has been mounted')
       })

       const counter = ref(0)

       const increment = () => counter.value++

       watch(counter, current => {
        if (current === 5) console.log('You have clicked five times!')
       })

       const arrayOfEmojis = computed(() => {
        Array.from(new Array(counter.value, () => props.emoji)).join(' ')
       })
       

       return {counter, increment, arrayOfEmojis}
    }
  }
</script>
<style scoped>

</style>
