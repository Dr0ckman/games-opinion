<template>
    <div>
        <h3>¿Quieres comprar coins para este juego?</h3>
        <button class="btn btn-warning">Agregar coins</button>
        <hr>
        <h3>Cantidad de coins comprados</h3>
        <div class="progress">
            <div class="progress-bar bg-danger" role="progressbar" style="width: 25%;" aria-valuenow="25"
                aria-valuemin="0" aria-valuemax="100">Description</div>
        </div>
        <hr>
        <h3>Estadísticas</h3>
        <div class="row">
            <div class="col px-2 py-2 bg-warning">% de finalización
                <hr>
                17%
            </div>
            <div class="col px-2 py-2 bg-success" style="color: white">Logros
                <hr>
                166
            </div>
            <div class="col px-2 py-2 bg-info">Recompensas
                <hr>
                200
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Monedero'
}

</script>

<style scoped lang="scss"></style>