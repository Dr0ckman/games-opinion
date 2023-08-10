<template>
    <footer class="footer mt-4">
        <p>Bárbara Pazos © 2023</p>
    </footer>
</template>

<style scoped lang="scss">
.footer {
    background-color: black;
    color: white;
    padding-left: 1rem;
    position: absolute;
    bottom: 0;
    width: 100%;

    p {
        padding-top: 1rem;
        opacity: 0.25;
    }
}
</style>

<script>
export default {
    name: 'Footer'
}
</script>