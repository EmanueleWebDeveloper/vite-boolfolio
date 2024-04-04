<script>
export default {
    name: 'ProjectCard',
    props: {
        title: String,
        type: String,
        content: String,
        technologies: Array,
    }
}
</script>

<template>

<div class="card py-2" style="width: 35rem;">
    <div class="d-flex justify-content-center">
        <div class="card-body my-3">
            <h3 class="card-title text-center fw-bold py-3">{{ title }}</h3>
            <p class="card-text text-center py-2"> <strong>Descrizione:</strong> {{ content }}</p>
            <p class="card-text text-center py-2"> <strong>Tipologia:</strong> {{ type }}</p>
            <p class="card-text text-center py-2" v-for="(element,index) in technologies" :key="index"> <strong>Linguaggi/Framework:</strong> {{ element.name }}</p>
        </div>
    </div>
</div>

</template>

<style>
ul li {
    list-style-type: none;
}

</style>