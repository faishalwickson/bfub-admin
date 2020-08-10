<template>
  <v-container>
    <h1>Halo, Admin!</h1>
    <p>Selamat datang di laman admin <br />BFUB UPI 2021</p>
    <Dashboard />
  </v-container>
</template>

<script>
import Dashboard from '@/components/Dashboard'
export default {
  components: {
    Dashboard,
  },
  head() {
    return {
      title: 'Dashboard',
    }
  },
}
</script>

<style scoped>
h1 {
  font-weight: bold;
}
p {
  font-weight: 600;
}
</style>
