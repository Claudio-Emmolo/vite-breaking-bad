<script>

export default {
    name: 'SingleCard',
    props: [
        'cardProperty',
    ]
}
</script>

<template>

    <article class="single-card">
        <div class="img-card position-relative">
            <div class="hover-card w-100 h-100 top-0 position-absolute">
                <div class="text-scroll m-auto">
                    <p class="m-auto">
                        {{ cardProperty.desc }}
                    </p>
                </div>
            </div>
            <img :src="cardProperty.card_images[0].image_url" :alt="cardProperty.name">
        </div>
        <div class="info-card text-center py-2">
            <h3 class="text-light fs-4 mb-3">{{ cardProperty.name }}</h3>
            <span>{{ cardProperty.archetype }}</span>
        </div>
    </article>

</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

article.single-card {
    width: calc(100% / 5 - 1rem);
    background-image: url('https://www.cardmaker.net/uploads/cardmaker_resources/1/backgrounds/fusion.png');
    margin: 0rem .5rem 1rem;
    border-radius: .5rem;
    box-shadow: rgba(0, 0, 0, 0.4) 0px 2px 4px, rgba(0, 0, 0, 0.3) 0px 7px 13px -3px, rgba(0, 0, 0, 0.2) 0px -3px 0px inset;

    div.img-card {
        position: relative;

        img {
            width: 100%;
        }

        div.hover-card {
            display: none;
            background-image: url('https://upload.wikimedia.org/wikipedia/en/2/2b/Yugioh_Card_Back.jpg?20201122212343');
            background-size: cover;

            img {
                width: 100%;
                height: 100%;
            }


            div.text-scroll {
                width: 80%;
                height: 75%;
                overflow-y: auto;

                p {
                    width: 90%;
                    height: 50%;
                    color: $white;
                    font-size: .9rem;
                }
            }
        }

        &:hover div.hover-card {
            display: flex;
        }
    }

}
</style>