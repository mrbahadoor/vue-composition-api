<template>
    <SettingsProvider>
        <ThemeButton />
    </SettingsProvider>
</template>
<script>
    import SettingsProvider from './SettingsProvider.vue'
    import ThemeButton from './ThemeButton.vue'

    export default {
        name: 'App',
        components: {
            SettingsProvider,
            ThemeButton
        }
    }
</script>