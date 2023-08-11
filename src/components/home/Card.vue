<template>
    <div class="card">
        <img class="card-img-top" :src="imgSrc" style="height: 18rem;">
        <div class="card-body">
            <h5 class="card-title">{{ title }}</h5>

        </div>
        <ul class="list-group list-group-flush">
            <li class="list-group-item">Rating: {{ rating }}</li>
            <li class="list-group-item">Fecha de lanzamiento: {{ released }}</li>
            <li class="list-group-item">Metacritic: {{ metacritic }}</li>
        </ul>
        <div class="card-body">
            <router-link to="/opiniones" class="btn btn-primary">Opinar</router-link>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        title: 'Titulo',
        rating: 'Rating',
        released: 'Fecha de lanzamiento',
        metacritic: 'Metacritic',
        imgSrc: ''
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.card {
    margin: 1rem auto;
}

.card-zone {
    overflow: hidden;
}
</style>
