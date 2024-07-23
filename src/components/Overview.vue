<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <div id="Overview" class="overview-area">
      <div class="container rubberBand">
        <div class="row align-items-center">
          <div class="col-lg-7 col-md-12">
            <div class="overview-content">
              <div class="card3">
                <span class="sub-title"
                  >Selamat Belajar & Jangan Lupa Berdo'a<br /><br /></span
                >
                <h2 style="font-size: 50px; font-weight: 600;">E-Modul Siklus Hidrologi Terintegrasi Ayat Al-Qur'an<br /></h2>
                <br />
                <p>Temukan Materi Yang Menarik Dan Bermanfaat Tentang Siklus Air Ini. <br />Selamat Belajar Dan Mari Eksplorasi Pengetahuan Bersama!
                </p>
              </div>
            </div>
          </div>
          <div class="col-lg-5 col-md-12">
            <div class="overview-content">
              <div class="carddd" style="padding-top: 100px;">
                <video
                  class="vid1"
                  autoplay
                  muted
                  loop
                  width="400"
                  play
                  src="../assets/Over-Viewnew.mp4"
                  type="video/mp4"
                  style="height: auto;"
                >
                  <!-- <source src="../assets/Over-Viewnew.mp4" type="video/mp4" /> -->
                  Your browser does not support HTML5 video.
                </video>
              </div>
            </div>
          </div>
          <div class="d-flex justify-content-center fadeIn">
        <video class="vid2" play loop controls vide id="myVideo" >
          <source src="../assets/Surat-ALbaqarah.mp4" type="video/mp4" />
          Your browser does not support HTML5 video.
        </video>
      </div>
        </div>
      </div>
    </div>
  </div>
</template>
<!-- eslint-disable prettier/prettier -->
<script>
export default {
  name: 'AppOverview',

  data() {
    return {
      time: 0,
    }
  },
}
</script>
