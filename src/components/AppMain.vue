<script>
import { store } from '../store.js';


export default {
    name: 'AppMain',
    data() {
        return {
            store
        }
    }
}

</script>

<template>
    <main>
        <section id="cards">
            <article class="single-card" v-for="cardItem in store.yuGiOhCards">
                <h3>{{ cardItem.name }}</h3>
            </article>
        </section>
    </main>
</template>

<style lang="scss" scoped>

</style>