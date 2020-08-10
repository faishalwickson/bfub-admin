<template>
  <v-app :style="{ backgroundImage: `url(${Image})`, backgroundSize: cover }">
    <Navbar />
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar'
import Image from '@/assets/images/bgAdmin.png'

export default {
  components: {
    Navbar,
  },
  data() {
    return {
      Image,
      cover: 'cover',
    }
  },
}
</script>

<style scoped>
body {
}
</style>
