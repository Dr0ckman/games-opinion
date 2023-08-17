<template>
    <div class="container-fluid">
        <h3>Introduzca sus datos:</h3>
    </div>

    <div class="float-end position-absolute start-50 top-50 translate-middle">
        <Login></Login>
    </div>
</template>

<script>
import Login from '@/components/login/Login.vue'

export default {
    name: 'LoginView',
    components: {
        Login
    },
    data() {
        return {
            name: String,
            lastName: String,
            game: String
        }
    }
}

</script>

<style scoped lang="scss">
.login-form {
    padding-left: 40%;
    padding-right: 40%;
}
</style>