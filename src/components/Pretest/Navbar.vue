<!-- eslint-disable prettier/prettier -->

<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light container-fluid">
    <router-link class="navbar-brand" to="/">
      <img class="black-logo" style="height: 50px" src="../../assets/img/logo.png" alt="Logo" />
    </router-link>

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
       
        <ul class="navbar-nav ">
          <li class="nav-item">
            <a class="nav-link">Halo {{ username }}!</a>
          </li> 
          <li @click="logout" class="nav-item">
            <a
              class="nav-link"
              >Logout</a>
          </li>
        </ul>

      </div>

  </nav>
</template>
<!-- eslint-disable prettier/prettier -->
<script>
import router from '@/router'
export default {
  name: 'AppNavbarPretest',

  data() {
    return {
      isSticky: false,
      active: false,
      button_active_state: false,
      username: JSON.parse(localStorage.getItem('user'))
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
  },
}
</script>
