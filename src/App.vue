<script>
import { store } from './store.js';
import axios from 'axios';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';



export default {
  components: {
    AppHeader,
    AppMain
  },

  data() {
    return {
      store,
      apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0',
    }
  },

  methods: {
    getApiElement() {

      axios.get(this.apiUrl, {
        params: {
        }
      })
        .then((response) => {
          console.log(response.data.data);
          this.store.yuGiOhCards = response.data.data
        })
        .catch((error) => {
          console.log(error);
        });
    }
  },

  created() {
    this.getApiElement()
  },
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
