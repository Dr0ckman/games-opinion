<template>
    <div class="float-start me-4">
        <div class="sidebar">
            <div class="container-fluid pt-3">
                <font-awesome-icon icon="fa-solid fa-user" size="lg" class="text-center"/>
                <br>
                <br>
                <span class="mb-1">Bienvenid@</span>
                <br>
                <strong>{{ $route.params.id }}</strong>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Sidebar',
    props: {
        name: String
    }
}
</script>

<style scoped lang="scss">
.sidebar {
    background-color: black;
    width: auto;
    height: 100vh;
    color: white;
    opacity: 0.9;
    // Margen negativo porque navbar tiene margen. 
    // Era esto o modificar todos los otros componentes.
    margin-top: -1.5rem;
}
</style>