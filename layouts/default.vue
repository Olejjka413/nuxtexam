<template>
  <v-app>
    <Header />
    <v-row>
      <v-col class="col-4 col-md-2">
        <nav class="d-flex flex-column mt-15 ml-5">
          <v-btn  class="mb-5">
            <nuxt-link to="/" class="black--text">Главная</nuxt-link>
          </v-btn>
         
          <v-btn  class="mb-5">
            <nuxt-link to="/events" class="black--text">События</nuxt-link>
          </v-btn>
           <v-btn  class="mb-5">
            <nuxt-link to="/about" class="black--text">О нас</nuxt-link>
          </v-btn>
        </nav>
        <div class="mt-10">
          <p class="text-center ml-5">Зарегистрировано погодных событий: 
            <span class="font-weight-bold h3">{{ eventsCount.events }}</span>
          </p>
          <v-img :src="require('~/static/left_widget_img.jpg')" width="250px" height="190px" class="ml-5"></v-img>
        </div>
      </v-col>
      <v-col class="col-10 col-sm-6 col-md-8">
        <nuxt />
      </v-col>
    </v-row>
    <Footer/>
  </v-app>
</template>

<script>
import Header from "@/components/Header"
import Footer from '~/components/Footer.vue'

export default {
  name: 'DefaultLayout',
  components: { Header,
  Footer },
  data: () => ({
    eventsCount: []
  }),
  async mounted() {
		this.eventsCount = await this.$axios.$get('https://demo-api.vsdev.space/api/elonus/left_widget')
	}
}
</script>

<style>

a {
  text-decoration: none;
}

</style>
