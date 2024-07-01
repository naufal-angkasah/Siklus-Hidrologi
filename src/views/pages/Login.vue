<!-- eslint-disable prettier/prettier -->
<template>
  <Preloader v-if="isLoading" />
  <loginb />
  <fuuter />
</template>

<script>
import loginb from '@/components/loginb.vue'
import Preloader from '@/components/Layouts/Preloader'
import fuuter from '@/components/Layouts/Footer.vue'
// import { uuid } from 'vue-uuid'
// import { useRouter } from 'vue-router'

// const router = useRouter()
// const route = useRoute()

export default {
  name: 'Login',
  components: {
    fuuter,
    Preloader,
    loginb,
  },
  data() {
    return {
      isLoading: true,
      visibleScrollableDemo: false,
      show: true,
    }
  },
  mounted() {
    setTimeout(() => {
      this.isLoading = false
    }, 2000)
  },
}
</script>
