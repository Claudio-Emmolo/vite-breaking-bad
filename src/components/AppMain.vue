<script>
import { store } from '../store.js';
import SingleCard from './SingleCard.vue';
import AppLoader from './AppLoading.vue'


export default {
    name: 'AppMain',

    components: {
        SingleCard,
        AppLoader
    },

    data() {
        return {
            store,
            loadCards: false
        }
    },

    methods: {

        loadWait() {

            setTimeout(() => {
                this.loadCards = true;

            }, 3000);
        }
    },

    created() {
        this.loadWait()
    }
}

</script>

<template>
    <main class="py-5">
        <section id="cards" class="container d-flex my-5 p-4 flex-column">
            <!-- Card Found -->

            <div class="card-found py-3">
                <span v-if="!loadCards" class="fw-bold ps-4">Found ... cards</span>
                <span v-else class="fw-bold ps-4">Found {{ store.yuGiOhCards.length }} cards</span>
            </div>

            <!-- Generated Cards -->
            <AppLoader v-if="(!loadCards) && (store.yuGiOhCards.length > 0)" class="m-auto" />

            <div v-else class="cards-container d-flex flex-wrap ">
                <!-- Import Cards -->
                <SingleCard v-for="cardItem in store.yuGiOhCards" :cardProperty="cardItem" />
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

main {
    background-image: url('https://wallpapercave.com/wp/wp2311074.png');
    background-repeat: no-repeat;
    background-size: cover;


    section#cards {
        background-color: $white;

        div.card-found {
            background-color: black;
            color: white;
            margin: 1rem .5rem 0;
        }

    }
}
</style>