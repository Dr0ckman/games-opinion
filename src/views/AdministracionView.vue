<template>
    <div>
        <Sidebar></Sidebar>
        <div class="container-fluid">
            <h1>Resumen de tu cuenta</h1>
            <p>Le diste me gusta al juego <strong>{{ this.$route.query.game }}</strong></p>
            <div>
                <Monedero></Monedero>
            </div>
        </div>
    </div>
</template>

<script>
import Sidebar from '@/components/administracion/Sidebar.vue'
import Monedero from '@/components/administracion/Monedero.vue'

export default {
    name: 'AdministracionView',
    components: {
        Sidebar,
        Monedero
    }    
}
</script>