<template>
    <div class="card">
        Component A
        <button @click="changeToggle">Toggle</button>
        <teleport to="#endofbody" :disabled="toggle">
            <p>Text from component A</p>
        </teleport>
    </div>
</template>
<script>
    import { ref } from 'vue';
    export default {
        setup() {            
            const toggle = ref(false)
            
            const changeToggle = () => { 
                toggle.value = !toggle.value;
                console.log('toggle', toggle.value);
            } 

            return {
                toggle,
                changeToggle
            }            
        }
    }
</script>
<style scoped>
    .card {
        display: table;
        margin: 20px auto;
        padding: 20px;
        border: green solid 1px;
    }
</style>