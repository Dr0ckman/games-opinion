<template>
    <div>
        <h3>¿Quieres comprar coins para este juego?</h3>
        <button id="agregar-coins" class="btn btn-warning" @click="updateCurrentValue()">
            <font-awesome-icon icon="fa-solid fa-coins" /> Agregar coins
        </button>
        <span :style="'display: ' + spanDisplay + '; opacity: 0.75'"><i> Cantidad máxima alcanzada</i></span>
        <hr>
        <h3>Cantidad de coins comprados</h3>
        <div class="progress">
            <div :class="'progress-bar ' + progressBarColor" role="progressbar" :style="'width: ' + String(currentValue * 2) + '%'">
                {{ currentValue }}
            </div>
        </div>
        <hr>
        <h3>Estadísticas</h3>
        <div class="row justify-content-between">
            <div class="col px-2 py-2 bg-warning">
                <font-awesome-icon icon="fa-solid fa-flag-checkered" />
                <strong> % de finalización</strong>
                <hr>
                17%
            </div>
            <div class="col px-2 py-2 bg-success" style="color: white">
                <font-awesome-icon icon="fa-solid fa-trophy" />
                <strong> Logros</strong>
                <hr>
                166
            </div>
            <div class="col px-2 py-2 bg-info">
                <font-awesome-icon icon="fa-solid fa-award" />
                <strong> Recompensas</strong>
                <hr>
                200
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Monedero',
    data() {
        return {
            currentValue: 0,
            progressBarColor: 'bg-success',
            spanDisplay: 'none'
        }

    },
    methods: {
        updateCurrentValue() {
            if (this.currentValue < 50) {
                this.currentValue++
                if(this.currentValue > 20 && this.currentValue <= 30) {
                    this.progressBarColor = 'bg-warning'
                }
                else if(this.currentValue > 30) {
                    this.progressBarColor = 'bg-danger'
                }
                else {
                    // pass
                }
            }
            else {
                document.querySelector('#agregar-coins').setAttribute('disabled', '')
                this.spanDisplay = 'inline'
            }
        }
    }
}

</script>

<style scoped lang="scss"></style>