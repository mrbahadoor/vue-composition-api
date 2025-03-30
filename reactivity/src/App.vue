<template>
 <div>Hi from vue 3</div> 
</template>

<script setup>
import { toRefs, defineProps, customRef } from 'vue'

const props = defineProps({
  a: { type: Number, default: 0 },
  b: { type: String, default: 'Vue 3!' },
  c: { type: Boolean, default: true },
})


const { a, b, c } = toRefs(props)

console.log(a.value, b.value, c.value)
// a.value = 1 // This will throw an error because props are readonly
// b.value = 'Hello' // This will also throw an error
// c.value = false // This will also throw an error

const email = customRef((track, trigger) => {
  let value = null

  return {
    get() {
      track()
      return value
    },
    set(newValue) {
      value = newValue
      trigger()
    }
  }
})

</script>
