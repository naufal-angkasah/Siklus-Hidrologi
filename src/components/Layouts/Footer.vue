<!-- eslint-disable prettier/prettier -->
<template>
  <footer class="footer-style-area pt-100">
  
    <div class="container">
      <div class="row justify-content-center animate__fadeInUpBig">
        <div class="col-sm-6 col-lg-3">
          <div class="single-footer-widget">
            <div class="footer-logo">
              <a :href="'#'">
                <img src="../../assets/img/logoupimerah.png" alt="Logo" />
              </a>
              <p>
                Jl. Dr. Setiabudi No.229, Isola, Kec. Sukasari, Kota Bandung,
                Jawa Barat 40154
              </p>
              <ul class="footer-social">
                <li>
                  <a :href="'https://web.facebook.com/upiofficial/'" target="_blank">
                    <i class="bi-facebook" style="padding-left: 1px"></i>
                  </a>
                </li>
                <li>
                  <a :href="'https://twitter.com/upi_official?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor'" target="_blank">
                    <i class="bi-twitter" style="padding-left: 1px"></i>
                  </a>
                </li>
                <li>
                  <a :href="'https://id.linkedin.com/school/universitas-pendidikan-indonesia/'" target="_blank">
                    <i class="bi-linkedin" style="padding-left: 1px"></i>
                  </a>
                </li>
                <li>
                  <a :href="'https://www.instagram.com/upiofficial/'" target="_blank">
                    <i class="bi-instagram" style="padding-left: 1px"></i>
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="col-sm-6 col-lg-2">
          <div class="single-footer-widget ps-3">
            <h3>Supporter.C</h3>
            <ul class="quick-link">
              <li>
                <a @click="scroll('Overview')" :href="'javascript:void(0)'"
                  >Overview</a
                >
              </li>
              <li>
                <a @click="scroll('Features')" :href="'javascript:void(1)'"
                  >Features</a
                >
              </li>
              <li>
                <a @click="scroll('Steps')" :href="''" disabled>Profile</a>
              </li>
              <li>
                <a
                  @click="scroll('Order')"
                  :href="'https://wa.me/qr/453O7X675IIWP1'" target="_blank"
                  >Order</a
                >
              </li>
            </ul>
          </div>
        </div>
        <div class="col-sm-6 col-lg-2">
          <div class="single-footer-widget ps-3">
            <h3>Company</h3>
            <ul class="quick-link">
              <li>
                <a :href="'https://www.upi.edu/'" target="_blank"
                  >Universitas Pendidikan Indonesia</a
                >
              </li>
              <li>
                <a :href="'https://www.upi.edu/about'" target="_blank"
                  >Magister pendidikan geografi UPI</a
                >
              </li>
            </ul>
          </div>
        </div>
        <div class="col-sm-6 col-lg-2">
          <div class="single-footer-widget ps-3">
            <h3>About Us</h3>
            <ul class="quick-link">
              <li>
                <a @click="scroll('Overview')" :href="'javascript:void(0)'"
                  >Supporter.C</a
                >
              </li>
              <li>
                <a
                  :href="'https://informatika.usk.ac.id/webinf/'"
                  target="_blank"
                  >Informatika USK</a
                >
              </li>
              <!-- <li>
                <a
                  :href="'https://maps.app.goo.gl/hjZuxKQxEbDdYG9e6'"
                  target="_blank"
                  >JL. Syech Abdurrauf No.3, Kopelma Darussalam, Kec. Syiah
                  Kuala, Kota Banda Aceh, Aceh 23111</a
                >
              </li> -->
            </ul>
          </div>
        </div>
        <div class="col-sm-6 col-lg-3">
          <div class="single-footer-widget">
            <h3>Contact Us</h3>
            <ul class="address-info">
              <li>
                <i class="bi-telephone-outbound"></i>
                <a :href="'tel:+6285262608383'" target="_blank"
                  >+62 852 6260 8383</a
                >
              </li>
              <li>
                <i class="bi-envelope"></i>
                <a :href="''">m.khairul311089@upi.edu</a>
              </li>
              <li>
                <i class="bi bi-whatsapp"></i>
                <a :href="'https://wa.me/qr/453O7X675IIWP1'" target="_blank"
                  >+62 852 6260 8383</a
                >
              </li>
            </ul>
          </div>
        </div>
      </div>
      <div class="copyright-style-area">
        <div class="row align-items-center">
          <div class="col-lg-6 col-md-6">
            <div class="copyright-item">
              <p>
                &copy; Copyright {{ currentYear }} By
                <a href="#">Supporter.C</a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>
<!-- eslint-disable prettier/prettier -->
<script>
export default {
  name: 'AppFooter',
  data() {
    return {
      currentYear: new Date().getFullYear(),
    }
  },
  mounted() {
    window.addEventListener('scroll', () => {
      if (window.scrollY >= 100) {
        this.isSticky = true
      } else {
        this.isSticky = false
      }
    })
  },
  methods: {
    scroll(refName) {
      const element = document.getElementById(refName)
      if (element) {
        element.scrollIntoView({ top: element.offsetTop, behavior: 'smooth' })
      }
    },
  },
}
</script>
