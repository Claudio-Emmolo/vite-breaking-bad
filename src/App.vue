<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';


export default {
  components: {
    AppHeader,
    AppMain
  }
}
</script>

<template>
  <!-- Import Header -->
  <AppHeader />
  <!-- Import Main -->
  <AppMain />
</template>

<style lang="scss">
// Import style / framework
@use 'bootstrap/scss/bootstrap.scss' as *;
@use './styles/general.scss' as *;
@use './styles/partials/variables' as *;

// Style
</style>
