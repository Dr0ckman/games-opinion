<template>
    <div>
        <Sidebar></Sidebar>
        <div class="container-fluid">
            <h1>Resumen de tu cuenta</h1>
            <p>Le diste me gusta al juego <strong>{{ this.$route.query.game }}</strong></p>
            <p>Acá va el componente para agregar monedas</p>
        </div>
    </div>
</template>

<script>
import Sidebar from '@/components/administracion/Sidebar.vue'
import Login from '@/components/login/Login.vue'

export default {
    name: 'AdministracionView',
    components: {
        Sidebar,
        Login
    }    
}
</script>