<script>
export default {
    name: 'ProjectCard',
    props: ['title', 'content', 'slug', 'type', 'technologies', 'image'],

}
</script>

<template>
<router-link :to="{name: 'single-project',  params: {slug: slug}}">

    <div class="card py-3" style="width: 35rem;">
        <div class="d-flex justify-content-center">
            <img class="card-img-top" :src=' `http://localhost:8000/storage/${image}` ' alt="card_image">

            <div class="card-body my-3">
                <h3 class="card-title text-center fw-bold py-3">{{ title }}</h3>
                <p class="card-text text-center py-2"> <strong>Descrizione:</strong> {{ content }}</p>
                <p class="card-text text-center py-2"> <strong>Tipologia:</strong> {{ type }}</p>
                
            </div>
        </div>
    </div>
</router-link>

</template>

<style>
ul li {
    list-style-type: none;
}

</style>