<template>
    <div class="container-fluid">
        <h3>Escribe tu opinión para el juego {{ $route.params.juego }}</h3>
        <form>
            <label for="name" class="form-label">Nombre</label>
            <input type="text" id="name" class="form-control">
            <br>
            <label for="opinion" class="form-label">Opinión</label>
            <textarea id="opinion" rows="5" class="form-control input-opinion"></textarea>
            <br>
            <input type="button" id="btn-agregar" class="btn btn-primary" value="Agregar" @click="agregarOpinion()">
        </form>
        <div v-if="visible" class="mt-5">
            <div class="accordion" id="accordionExample">
                <div class="accordion-item">
                    <h2 class="accordion-header" id="headingOne">
                        <button class="accordion-button" type="button" data-bs-toggle="collapse"
                            data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
                            {{ title }}
                        </button>
                    </h2>
                    <div id="collapseOne" class="accordion-collapse collapse show" aria-labelledby="headingOne"
                        data-bs-parent="#accordionExample">
                        <div class="accordion-body">
                            {{ content }}
                        </div>
                    </div>
                </div>
            </div>
            <button id="btn-eliminar" class="btn btn-danger me-2 mt-4" @click="borrarOpinion()">
                Eliminar
            </button>
            <button id="btn-editar" class="btn btn-warning ms-2 mt-4" @click="editarOpinion()">
                Editar
            </button>
        </div>
        <div v-if="!visible" class="mt-5">
            <div class="alert alert-warning" role="alert">
                <strong>No hay opiniones disponibles</strong>
            </div>
        </div>
    </div>
</template>
  
<script>

export default {
    name: 'NuevaOpinion',
    components: {
        Opinion
    },
    data() {
        return {
            visible: false,
            title: '',
            content: ''
        }
    },
    methods: {
        borrarOpinion() {
            this.visible = false
            this.title = ''
            this.content = ''
            this.$el.querySelector("#btn-agregar").value = "Agregar"
            this.$el.querySelector('#name').value = ''
            this.$el.querySelector('#name').removeAttribute("disabled")
            this.$el.querySelector('#opinion').value = ''
            this.$el.querySelector('#opinion').removeAttribute("disabled")
            this.$el.querySelector('#btn-agregar').removeAttribute("disabled")
            this.$el.querySelector('#name').focus()
        },
        agregarOpinion() {
            this.visible = true
            this.title = this.$el.querySelector('#name').value
            this.content = this.$el.querySelector('#opinion').value
            this.$el.querySelector('#name').value = ''
            this.$el.querySelector('#name').setAttribute("disabled", "")
            this.$el.querySelector('#opinion').value = ''
            this.$el.querySelector('#opinion').setAttribute("disabled", "")
            this.$el.querySelector('#btn-agregar').setAttribute("disabled", "")
        },
        editarOpinion() {
            this.$el.querySelector("#btn-agregar").value = "Actualizar"
            this.$el.querySelector('#name').value = ''
            this.$el.querySelector('#name').removeAttribute("disabled")
            this.$el.querySelector('#opinion').value = ''
            this.$el.querySelector('#opinion').removeAttribute("disabled")
            this.$el.querySelector('#btn-agregar').removeAttribute("disabled")
            this.$el.querySelector('#name').focus()
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
  