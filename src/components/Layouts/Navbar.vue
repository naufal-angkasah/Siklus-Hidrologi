<!-- eslint-disable prettier/prettier -->

<template>
  <nav
    toggleable="lg"
    :class="[
      'main-navbar navbar navbar-expand-md navbar-light',
      { 'is-sticky': isSticky },
    ]"
  >
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/">
        <img
          class="black-logo"
          style="height: 50px"
          src="../../assets/baru/Logo.png"
          alt="Logo"
        />
      </router-link>

      <!-- <b-navbar-toggle target="nav-collapse"></b-navbar-toggle> -->

      <div
        class="navbar-toggler"
        @click="active = !active"
        :aria-pressed="active ? 'true' : 'false'"
        v-bind:class="{ active: button_active_state }"
        v-on:click="button_active_state = !button_active_state"
      >
        <i class="bi bi-list"></i>
        <i class="bi bi-x"></i>
      </div>

      <div :class="{ 'collapse navbar-collapse': true, toggler: active }">
        <ul class="navbar-nav">
          <li class="nav-item">
            <a
              class="nav-link"
              @click="scroll('Overview')"
              href="javascript:void(0)"
              >Home</a
            >
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              @click="scroll('Informasi')"
              href="javascript:void(1)"
              >Informasi Umum
            </a>
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              @click="scroll('Komponen')"
              href="javascript:void(5)"
              >Komponen Inti</a
            >
          </li>
          <li class="nav-item">
            <a
              class="nav-link"
              @click="scroll('Kegiatan')"
              href="javascript:void(2)"
              >Kegiatan Pembelajaran</a
            >
          </li>

          <li class="nav-item">
            <a
              class="nav-link"
              @click="
                () => {
                  warning = true
                }
              "
              >Logout</a
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
  <CModal
    backdrop="static"
    :visible="warning"
    @close="
      () => {
        warning = false
      }
    "
    aria-labelledby="StaticBackdropExampleLabel"
  >
    <CModalHeader>
      <CModalTitle id="StaticBackdropExampleLabel">Konfirmasi</CModalTitle>
    </CModalHeader>
    <CModalBody>
      <center><CIcon icon="cilWarning" size="8xl" /></center>
      <br />
      <h6>Apakah anda sudah melihat isi Pertemuan 1?</h6></CModalBody
    >
    <CModalFooter>
      <CButton color="danger" @click="logout"> Tetap Logout </CButton>
      <CButton color="info" @click="P1"> Masuk Pertemuan 1 </CButton>
    </CModalFooter>
  </CModal>
</template>
<!-- eslint-disable prettier/prettier -->
<script>
import router from '@/router'
import { CIcon } from '@coreui/icons-vue'

// import AppHeaderDropdownAccnt from '@/Pertemuan1/components/AppHeaderDropdownAccnt.vue'

export default {
  name: 'AppNavbar',
  components: {
    // AppHeaderDropdownAccnt,
    CIcon,
  },
  data() {
    return {
      isSticky: false,
      active: false,
      button_active_state: false,
      warning: false,
    }
  },
  mounted() {
    const that = this
    window.addEventListener('scroll', () => {
      let scrollPos = window.scrollY
      if (scrollPos >= 100) {
        that.isSticky = true
      } else {
        that.isSticky = false
      }
    })
  },
  methods: {
    logout() {
      localStorage.clear()
      router.push({ name: 'Login' })
    },
    scroll(refName) {
      const element = document.getElementById(refName)
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
      }
    },
    P1() {
      router.push({ name: 'Pertemuan1' })
    },
  },
}
</script>
