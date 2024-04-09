<script>
export default {
    name: 'ProjectCard',
    props: ['title', 'content', 'slug', 'type', 'technologies', 'image'],

}
</script>

<template>
    <router-link :to="{ name: 'single-project', params: { slug: slug } }">

        <div class="card" style="width: 18rem;">
            <img class="card-img-top" :src='image' alt="card_image">
            <div class="card-body">
                <h5 class="card-title">{{ title }}</h5>
               
                <p class="card-text"><strong>Descrizione:</strong> {{ content }}</p>
                <p class="card-text"><strong>Tipologia:</strong> {{ type }}</p>

            </div>
        </div>


    </router-link>
</template>

<style>
ul li {
    list-style-type: none;
}
</style>