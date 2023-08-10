<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <h1>Títulos disponibles</h1>
      </div>
    </div>
    <div class="row">
      <div class="col-lg-4 col-md-12">
        <Card title="Título 1" content="Contenido 1" />
      </div>
      <div class="col-lg-4 col-md-12">
        <Card title="Título 2" content="Contenido 2" />
      </div>
      <div class="col-lg-4 col-md-12">
        <Card title="Título 3" content="Contenido 3" />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Card from '@/components/home/Card.vue'

export default {
  name: 'HomeView',
  components: {
    Card
  }
}
</script>
