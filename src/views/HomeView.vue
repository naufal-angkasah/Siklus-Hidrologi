<!-- eslint-disable prettier/prettier -->
<template>
  <!-- taukah kamu -->
  <div><Preloader v-if="isLoading" /></div>
  <div>
    <Navbar />
    <Overview />
    <Informasi />
    <ProfilPancasila />
    <asidee />
    <Komponen />
    <Kegiatan />
    <Order />
    <features />
    <Futer />
  </div>
</template>
<!-- eslint-disable prettier/prettier -->
<script>
import Preloader from '@/components/Layouts/Preloader'
import Navbar from '@/components/Layouts/Navbar.vue'
import Futer from '@/components/Layouts/Footer.vue'
import Overview from '@/components/Overview.vue'
import Features from '@/components/Features.vue'
import asidee from '@/components/aside.vue'
import Informasi from '@/components/InformasiUmum.vue'
import Order from '@/components/Order.vue'
import Kegiatan from '@/components/KegiatanPembelajaran.vue'
import Komponen from '@/components/KomponenInti.vue'
import ProfilPancasila from '@/components/P5.vue'

export default {
  name: 'HomeView',
  components: {
    Preloader,
    Navbar,
    Overview,
    Informasi,
    Futer,
    Features,
    Komponen,
    Kegiatan,
    Order,
    ProfilPancasila,
    asidee,
  },
  data() {
    return {
      isLoading: true,
      
    }
  },
  mounted() {
    setTimeout(() => {
      this.isLoading = false   
    }, 2000)
  },
  
}
</script>
