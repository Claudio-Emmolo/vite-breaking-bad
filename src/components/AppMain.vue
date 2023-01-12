<script>
import CardList from './CardList.vue';


export default {
    name: 'AppMain',

    components: {
        CardList,
    },


}

</script>

<template>
    <main class="py-5">
        <section id="cards" class="container d-flex my-5 p-4 flex-column">

            <CardList />

        </section>
    </main>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

main {

    section#cards {
        background-color: $white;

    }
}
</style>