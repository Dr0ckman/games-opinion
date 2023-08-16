<template>
    <div class="container-fluid">
        <h3>Escribe tu opinión para el juego {{ $route.params.juego }}</h3> <!-- Toma el nombre del juego de la URL -->
        <form>
            <label for="name" class="form-label">Nombre</label>
            <input type="text" id="name" class="form-control">
            <br>
            <label for="opinion" class="form-label">Opinión</label>
            <textarea id="opinion" rows="5" class="form-control input-opinion"></textarea>
            <br>
            <!-- Llama agregarOpinion o actualizarOpinion dependiendo del nombre del botón -->
            <input type="button" id="btn-agregar" class="btn btn-primary" value="Agregar"
                @click="handleOpinion(indexHelper)">
        </form>
        <!-- Itera listaOpiniones e inserta componentes de forma dinámica -->
        <div id="accordion-zone" class="mt-5">
            <div v-for="(opinion, index) in listaOpiniones">
                <div>
                    <AcordeonOpinion :title="opinion.title" :content="opinion.content + ' (Index: ' + String(index) + ')'"
                        :index="index"></AcordeonOpinion>
                    <div class="mt-2">
                        <button class="btn btn-danger me-4" @click="eliminarOpinion(index)">Eliminar</button> <!-- Elimina opiniones de listaOpiniones.
                        El ciclo for de arriba se encarga de quitarlo de la vista -->
                        <button class="btn btn-warning" @click="editarOpinion(index)">Editar</button> <!-- Copia los contenidos de la opinión 
                        a los input, cambia el nombre del botón de "agregar" a "actualizar", cambia el foco al primer input
                        y pasa el valor de index a indexHelper -->
                    </div>
                </div>

            </div>
        </div>
        <div class="mt-5"> <!-- Muestra la alerta sólo cuando no hay opiniones en listaOpiniones. Se usa
        el lifecycle hook beforeUpdate más abajo -->
            <div class="alert alert-warning" role="alert" v-show="!hideAlert">
                <strong>No hay opiniones disponibles</strong>
            </div>
        </div>
    </div>
</template>
  
<script>

import AcordeonOpinion from './AcordeonOpinion.vue'

export default {
    name: 'NuevaOpinion',
    components: {
        AcordeonOpinion
    },
    data() {
        return {
            listaOpiniones: [],
            hideAlert: false,
            indexHelper: Number
        }

    },
    methods: {
        handleOpinion(index) {
            if (document.querySelector('#btn-agregar').value === "Agregar") {
                this.agregarOpinion()
            }
            else { this.actualizarOpinion(index) }
        },
        agregarOpinion() { // Agrega una opinión a listaOpiniones
            let opinionTitle = document.querySelector("#name").value
            let opinionContent = document.querySelector("#opinion").value

            if (opinionTitle !== '' && opinionContent !== '') {
                this.listaOpiniones.push({ title: opinionTitle, content: opinionContent })
            }
            else {
                alert("Favor completar los campos requeridos")
            }

            document.querySelector("#name").value = ''
            document.querySelector("#opinion").value = ''
        },
        actualizarOpinion(index) {
            let opinionTitle = document.querySelector("#name").value
            let opinionContent = document.querySelector("#opinion").value

            if (opinionTitle !== '' && opinionContent !== '') {
                this.listaOpiniones[index] = { title: opinionTitle, content: opinionContent }
                console.log(this.listaOpiniones)
            }
            else {
                alert("Favor completar los campos requeridos")
            }

            document.querySelector("#name").value = ''
            document.querySelector("#opinion").value = ''
            document.querySelector("#btn-agregar").value = "Agregar"
        },
        eliminarOpinion(index) {
            this.listaOpiniones.splice(index, 1)
            console.log(this.listaOpiniones)
        },
        editarOpinion(index) {
            document.querySelector("#name").value = this.listaOpiniones[index].title
            document.querySelector("#opinion").value = this.listaOpiniones[index].content

            document.querySelector("#btn-agregar").value = 'Actualizar'

            document.querySelector("#name").focus()

            this.indexHelper = index
        }
    },
    beforeUpdate() {
        console.log(this.listaOpiniones)
        if (this.listaOpiniones.length !== 0) {
            this.hideAlert = true
        }
        else {
            this.hideAlert = false
        }
    }
}



</script>

  <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.form-control {
    max-width: 20rem;
}
</style>
  