<template>
  <div v-if="info">
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <h1>Títulos disponibles</h1>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-4 col-md-12">
          <Card :title="info[5].name" :rating="info[5].rating" :released="info[5].released"
            :metacritic="info[5].metacritic" :imgSrc="info[5].background_image" />
        </div>
        <div class="col-lg-4 col-md-12">
          <Card :title="info[6].name" :rating="info[6].rating" :released="info[6].released"
            :metacritic="info[6].metacritic" :imgSrc="info[6].background_image" />
        </div>
        <div class="col-lg-4 col-md-12">
          <Card :title="info[7].name" :rating="info[7].rating" :released="info[7].released"
            :metacritic="info[7].metacritic" :imgSrc="info[7].background_image" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import Card from '@/components/home/Card.vue'
import axios from 'axios'

export default {
  name: 'HomeView',
  data() {
    return {
      info: ''
    }
  },
  components: {
    Card
  },
  created() {
    axios
      .get('https://api.rawg.io/api/games?key=3b453ce7a095449c801f2e37866b0924&page=2')
      .then(response => (this.info = response.data.results))
  }
}
</script>
