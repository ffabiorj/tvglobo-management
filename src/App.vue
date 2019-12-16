<template>
  <v-app class="grey light-4">
    <Navbar />
    <v-content>
    <Table />
      <router-view></router-view>      
    </v-content>
    <Footer />
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar'
import Table from '@/components/Table'
import Footer from '@/components/Footer'

export default {
  name: 'App',
  components: {Navbar, Table, Footer},
  data: () => ({
    //
  }),
};
</script>
