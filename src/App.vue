<script>
import DynamicPicture from './components/dynamicPicture.vue'

export default {
  components: {
    DynamicPicture
  },
  data() {
    return {
      pictures: [
        { "id": "0", "url": "https://picsum.photos/200/300", "width": 200 },
        { "id": "1", "url": "https://picsum.photos/300/300", "width": 300 },
        { "id": "2", "url": "https://picsum.photos/350/300", "width": 350 },
        { "id": "3", "url": "https://picsum.photos/400/300", "width": 400 },
        { "id": "4", "url": "https://picsum.photos/450/300", "width": 450 },
        { "id": "5", "url": "https://picsum.photos/500/300", "width": 500 },
        { "id": "6", "url": "https://picsum.photos/600/300", "width": 600 },
        { "id": "7", "url": "https://picsum.photos/350/300", "width": 350 },
        { "id": "8", "url": "https://picsum.photos/450/300", "width": 450 },
        { "id": "9", "url": "https://picsum.photos/358/300", "width": 358 },
        { "id": "10", "url": "https://picsum.photos/700/300", "width": 700 },
        { "id": "11", "url": "https://picsum.photos/200/300", "width": 200 },
        { "id": "12", "url": "https://picsum.photos/200/300", "width": 200 },
      ]
      ,
    }
  },
  // methods: {
  //   async fetchPictures() {
  //     const data = await fetch(`https://pixabay.com/api/?key=${import.meta.env.VITE_PIXABAY_API_KEY}&orientation=horizontal`)
  //     this.pictures = await data.json()
  //   }
  // },
  // mounted() {
  //   this.fetchPictures()
  // }
}
</script>

<template>
  <main>
    <div class="p-4">
      <h1>Helium images</h1>
      <div class="flex flex-wrap flex-row p-8">
        <DynamicPicture v-for="picture in pictures" :key="picture.id" :custom-margin=4 :image-width="picture.width"
          :picture-data="picture" />
        <div class="remain_space_ctrl"></div>
      </div>
    </div>
  </main>
</template>

<style>
.remain_space_ctrl {
  background: transparent;
  flex-grow: 10000000 !important;
}
</style>
