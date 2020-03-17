<template>
  <div>
    <h1>Photo Gallery</h1>
    <router-link 
      :to="{
        name: 'PhotosGallery',
        params: {
          id: photo
        }
      }"
      v-for="(photo, index) of arrayPhotos" :key="index"
    >
      <button>Photo <span v-text="photo"></span></button>
    </router-link>
    <Photo />
    <button @click="goPrevious">Previos</button>
    <button @click="goHome">Home</button>
    <button @click="goNext">Next</button>
  </div>
</template>

<script>
  import Photo from '../components/Photo';
  export default {
    components: {
      Photo
    },
    data() {
      return {
        arrayPhotos: [1,2,3],
      }
    },
    methods: {
      goPrevious() {
        this.$router.go(-1);
      },
      goHome() {
        this.$router.push('/');
      },
      goNext() {
        this.$router.go(1);
      }
    }
  }
</script>