<script>

export default {
    name: 'HeaderApp',
    components: {

    },
    methods: {

    },
    mounted() {

    },
}
</script>

<template>
    <header>
        <nav class="navbar navbar-expand-lg navbar-dark"
            style="background: linear-gradient(to right, #343a40, #6c757d);">
            <div class="container">
                <a class="navbar-brand me-5" href="#">My Portfolio</a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false"
                    aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse justify-content-end" id="navbarNavAltMarkup">
                    <div class="navbar-nav">

                        <li>
                            <router-link :to="{ name: 'home' }" class="nav-link">
                                Home
                            </router-link>
                        </li>
                        <li>
                            <router-link :to="{ name: 'blog' }" class="nav-link">
                                All Projects
                            </router-link>
                        </li>

                        <li>
                            <router-link :to="{ name: 'contact-us' }" class="nav-link">
                                contatti
                            </router-link>
                        </li>

                    </div>
                </div>
            </div>
        </nav>
    </header>
</template>

<style scoped>
header {
    background-color: #363c42;
    padding-top: 10px;
    padding-bottom: 10px;
}

.navbar-brand {
    font-size: 1.5rem;
}

.navbar-nav .nav-link {
    padding: 0.5rem 1rem;
    margin: 0 10px;
}

.navbar-nav .nav-link:hover {
    color: #0d6efd;
}
</style>