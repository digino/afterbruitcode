<script>
import DynamicPicture from './components/dynamicPicture.vue'

export default {
  components: {
    DynamicPicture
  },
  data() {
    return {
      pictures: [],
    }
  },
  methods: {
    async fetchPictures() {
      const data = await fetch(`https://pixabay.com/api/?key=${import.meta.env.VITE_PIXABAY_API_KEY}&orientation=horizontal`)
      this.pictures = await data.json()
    }
  },
  mounted() {
    this.fetchPictures()
  }
}
</script>

<template>
  <main>
    <div class="p-4">
      <h1>Helium images</h1>
      <div class="flex flex-wrap flex-row">
        <DynamicPicture v-for="picture in pictures.hits" :key="picture.id" :custom-margin=4 :image-width="picture.webformatWidth"
          :picture-data="picture" />
      </div>
    </div>
  </main>
</template>
