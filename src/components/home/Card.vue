<template>
        <div class="card">
            <div class="card-img-top bg-primary placeholder" style="height: 10rem;"></div>
            <div class="card-body">
                <h5 class="card-title">{{ title }}</h5>
                <p class="card-text">{{ content }}
                </p>
                <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
        </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        title: String,
        content: String,
        imgSrc: String
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
