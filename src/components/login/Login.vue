<template>
    <div class="container-fluid">
        <div class="mb-3">
            <label for="name" class="form-label">Nombre</label>
            <input type="text" name="name" id="name" class="form-control mb-3">
            <label for="name" class="form-label">Apellido</label>
            <input type="text" name="lastName" id="last-name" class="form-control mb-3">
            <input type="button" value="Ingresar" class="btn btn-primary" @click=buttonHandler()>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Login',
    methods: {
        buttonHandler() {
            if (document.querySelector('#name').value !== '' && document.querySelector('#last-name').value !== '') {
                this.$router.replace({
                    name: 'administracion',
                    params: { id: String(document.querySelector('#name').value) + ' ' + String(document.querySelector('#last-name').value) },
                    query: { game: this.$route.query.game }
                })

            }
            else {
                alert('Complete los datos requeridos')
            }

        }
    }
}
</script>