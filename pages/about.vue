<template>
  <v-container class="d-flex">
    <p class=" ml-15 mt-10">{{ indexContent.text }}</p>
    <v-img class="mt-10 ml-10" width="300" :src="indexContent.image"></v-img>
  </v-container>
</template>

<script>
export default {
  name: 'AboutPage',
  data: () => ({
    indexContent: []
  }),
  async mounted() {
		this.indexContent = await this.$axios.$get('https://demo-api.vsdev.space/api/elonus/about_page')
	}
}
</script>
<style scoped>

</style>