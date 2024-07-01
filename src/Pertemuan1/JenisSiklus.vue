<style scoped>
video {
  width: 65%;
  height: auto;
  border-radius: 10px;
  @media only screen and (max-width: 991px) {
    width: 100%;
    height: auto;
  }
}
img {
  width: 65%;
  height: auto;
  @media only screen and (max-width: 991px) {
    width: 100%;
    height: auto;
  }
}
</style>
<template>
  <CRow>
    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>Jenis Siklus Air</strong>
        </CCardHeader>
      </CCard>
    </CCol>
    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>Siklus Pendek Hujan</strong>
        </CCardHeader>
        <CCardBody>
          <br />
          <!-- <p>Ilustrasi Siklus Pendek :</p> -->
          <div>
            <center>
              <div class="choose-image">
                <img src="../assets/images/Sikluspendek.png" alt="image" />
              </div>
            </center>
            <br />
            <h6>
              Sumber : Adaptasi E-Modul Siklus Hidrologi Guru Geografi
              <a href="https://smaalfacentauri.sch.id/" target="_blank">
                SMA Alfa Centauri Bandung</a
              >
            </h6>
          </div>
          <br />
          <h6>Siklus Pendek Hujan:</h6>
          <h6>
            <ul>
              <li>
                <strong>Deskripsi :</strong><br />Sinar matahari memanaskan
                permukaan laut, menyebabkan penguapan yang meningkat. Setelah
                mencapai ketinggian tertentu, udara mendingin di sekitar
                permukaan laut dan terjadi kondensasi, membentuk awan. Ini dapat
                mengakibatkan hujan di wilayah tersebut.
              </li>
              <li>
                <strong>Contoh Kontekstual di Indonesia : </strong><br />Di
                wilayah Indonesia, seperti di sekitar Kepulauan Nusa Tenggara,
                panas matahari yang intens menyebabkan penguapan yang signifikan
                dari permukaan laut. Ketika uap air mencapai ketinggian di
                atmosfer, terjadi kondensasi dan pembentukan awan. Akibatnya,
                hujan sering terjadi, memberikan pasokan air yang penting bagi
                pertanian dan kehidupan sehari-hari penduduk setempat.
              </li>
            </ul>
          </h6>
        </CCardBody>
      </CCard>
    </CCol>
    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>Siklus Sedang Hujan</strong>
        </CCardHeader>
        <CCardBody>
          <br />
          <!-- <p>Ilustrasi Siklus Sedang :</p> -->
          <div>
            <center>
              <div class="choose-image">
                <img src="../assets/images/Siklussedang.png" alt="image" />
              </div>
            </center>
            <br />
            <h6>
              Sumber : Adaptasi E-Modul Siklus Hidrologi Guru Geografi
              <a href="https://smaalfacentauri.sch.id/" target="_blank">
                SMA Alfa Centauri Bandung</a
              >
            </h6>
          </div>
          <br />
          <h6>Siklus Sedang Hujan:</h6>
          <h6>
            <ul>
              <li>
                <strong>Deskripsi :</strong><br />Panas matahari menyebabkan
                penguapan air laut, yang kemudian terbawa oleh angin ke daratan.
                Udara dingin di atas daratan menyebabkan kondensasi dan
                pembentukan awan, yang akhirnya menghasilkan hujan. Air hujan
                kemudian mengalir kembali ke laut setelah menyuburkan daratan.
              </li>
              <li>
                <strong>Contoh Kontekstual di Indonesia: </strong><br />Di
                dataran tinggi Papua, sinar matahari yang kuat memanaskan
                perairan di sekitarnya, memicu penguapan yang signifikan. Angin
                membawa uap air tersebut ke pegunungan, di mana udara dingin
                menyebabkan terjadinya hujan. Air hujan ini kemudian mengalir ke
                sungai-sungai yang menghidupkan kehidupan di sekitarnya sebelum
                akhirnya kembali ke laut.
              </li>
            </ul>
          </h6>
        </CCardBody>
      </CCard>
    </CCol>
    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>Siklus Panjang Hujan</strong>
        </CCardHeader>
        <CCardBody>
          <br />
          <!-- <p>Ilustrasi Siklus Panjang :</p> -->
          <div>
            <center>
              <div class="choose-image">
                <img src="../assets/images/Sikluspanjang.png" alt="image" />
              </div>
            </center>
            <br />
            <h6>
              Sumber : Adaptasi E-Modul Siklus Hidrologi Guru Geografi
              <a href="https://smaalfacentauri.sch.id/" target="_blank">
                SMA Alfa Centauri Bandung</a
              >
            </h6>
          </div>
          <br />
          <h6>Siklus Panjang Hujan:</h6>
          <h6>
            <ul>
              <li>
                <strong>Deskripsi :</strong><br />Sinar matahari menyebabkan
                penguapan air laut, yang kemudian terbawa oleh angin ke daratan.
                Setelah mengalami pendinginan, uap air tersebut berubah menjadi
                kristal salju, turun sebagai hujan salju, dan akhirnya membentuk
                gletser atau padang salju. Air yang mencair mengalir kembali ke
                laut.
              </li>
              <li>
                <strong>Contoh Kontekstual di Indonesia : </strong
                ><br />Meskipun Indonesia terletak di daerah tropis, beberapa
                wilayah seperti di pegunungan Jayawijaya di Papua memiliki
                ketinggian yang cukup untuk mengalami fenomena hujan salju. Di
                sana, sinar matahari yang kuat memicu penguapan dari perairan di
                sekitarnya. Uap air tersebut terbawa oleh angin ke puncak-puncak
                gunung yang tinggi, di mana udara dingin menyebabkan pembentukan
                hujan salju. Ini kemudian membentuk gletser yang menjadi sumber
                air penting bagi ekosistem dan kehidupan manusia di sekitar
                Pegunungan Jayawijaya
              </li>
            </ul>
          </h6>
        </CCardBody>
      </CCard>
    </CCol>
  </CRow>
</template>

<script>
import VueImg from '@/assets/images/vue.jpg'
export default {
  name: 'Cards',
  setup() {
    return {
      VueImg,
    }
  },
}
</script>
