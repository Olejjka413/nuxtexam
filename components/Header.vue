<template>
	<v-container fluid>
      <v-app-bar
      color="orange"
      class="d-flex"
      >	
        <v-img :src="require('~/static/earthquake_img.jpg')" class="mr-3 ml-5" height="40" width="40" />
        <h1 class="ml-60 text-uppercase">Илонус</h1>
        <h2 class="ml-15 text-uppercase"> Регистрация погодных событий на Марсе</h2>
      </v-app-bar>
    </v-container>
</template>

<script>
export default {
  name: "Header"
}
</script>
