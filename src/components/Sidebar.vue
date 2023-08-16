<template>
    <div class="float-start me-4">
        <div class="sidebar">
            <div class="container-fluid pt-3">
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
    margin-top: -1.5rem;
}
</style>