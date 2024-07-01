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
          <strong>Manfaat Siklus Air </strong
          ><small>(Element Daya Guna Air)</small>
        </CCardHeader>
        <CCardBody>
          <p>
            <strong>Begitu besar manfaat dari Siklus Hidrologi</strong>
          </p>
          <h6>
            ⮚ Terjadinya siklus air memberikan manfaat bagi makhluk hidup:
            manusia, hewan dan tumbuhan, yaitu :
          </h6>
          <h6>
            <ul type="square">
              <li>
                Untuk merjaga ketersediaan air di bumi, mendistribusikan air
                keseluruh penjuru muka bumi baik yang berada di dataran tinggi
                maupun dataran rendah. Menyediakan air bersih yang sangat
                dibutuhkan untuk kehidupan makhluk hidup.
              </li>
              <li>
                Pada Tumbuhan menghasilkan berbagai macam buah-buahan,
                biji-bijian dan tanaman lain, hal ini adalah rezeki pemberian
                Tuhan yang Maha pemurah dan kuasa kepada Makhluk lainnya baik
                dimnafaatkan manusia atau ternak.
              </li>
              <li>
                Selain itu air hujan akan menyerap ke dalam tanam, dan mengalir
                membentuk sungai dari daratan tinggi (gunung) menuju ke daerah
                rendah kemudian terkumpul yaitu terbentuk danau dan air laut.
              </li>
              <li>
                Yang menariknya dari siklus hidrologi ini yaitu bahwa hujan
                tidak akan pernah berhenti. Dari proses tersebut hujan dapat
                diprediksi kapan akan turunnya dan kapan akan berakhirnya. Namun
                hujan tidak akan berhenti selamanya. Karena hujan meruapan salah
                satu ciptaan Tuhan yang Maha Besar untuk alam semesta ini.
              </li>
            </ul>
          </h6>
          <h6>
            ⮚ Hal ini bearti air senantiasa berputar dalam suatu siklus yang
            seimbang menurut ukuran dan kadarnya. Sehingga kehidupan dibumi
            bergantung pada siklus air ini.
          </h6>
          <strong>Manfaat siklus hidrologi terdapat dalam surat :</strong>
          <br />
          <ol type="1">
            <li>Al-A’raf ayat 57</li>
            <li>Al- Anfal ayat 11</li>
            <li>An-Nahl ayat 10</li>
            <li>Az-Zukhruf ayat 11</li>
          </ol>

          <!-- <h6>Ilustrasi Manfaat Sikllus :</h6> -->
          <center>
            <div>
              <video class="vid2" play controls loop width="300" id="myVideo">
                <source
                  src="@/assets/video/manfaathujan.mp4"
                  type="video/mp4"
                />
                Your browser does not support HTML5 video.
              </video>
              <h6>
                Sumber : Peneliti ( berbantuan
                <a href=" https://www.canva.com/" target="_blank"> Canva</a>
                )
              </h6>
            </div>
          </center>
        </CCardBody>
      </CCard>
    </CCol>
    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>Manfaat Lainnya </strong
          ><small>(Element Daya Guna Air)</small>
        </CCardHeader>
        <CCardBody>
          <h6>
            Manfaat Lain dari siklus Hidrologi yang sangat potensial di
            Indonesia bahkan menjadi perbincangan dunia, salah satunya tentang
            perkembangan energi baru dan terbarukan (EBT). Kapasitasnya untuk
            menyediakan sumber energi yang berkelanjutan dan ramah lingkungan,
            serta mengurangi ketergantungan pada bahan bakar fosil yang semakin
            terbatas. Indonesia memiliki potensi pengembangan pembangkit listrik
            tenaga air (PLTA). Indonesia berkomitmen untuk meningkatkan energi
            baru dan terbarukan hingga 23% sebagai pemasok energinya di tahun
            2025.
          </h6>
          <h6>
            Energi Air atau Hydropower merupakan energi yang dihasilkan oleh
            pergerakan air yang memutar turbin. Sumber energi dari aliran air
            ini paling sering digunakan di Indonesia dengan memanfaatkan aliran
            air sungai. Potensi di Indonesia adalah 19.385 MW dengan kapasitas
            terpasang hingga tahun 2020 adalah 6.121 MW. Total kapasitas
            terpasang saat ini menjadikan energi air sebagai penyumbang bauran
            energi terbarukan terbesar di Indonesia. <br />Pembangkit terbaru
            dari energi air adalah yang terpasang di Poso, Sulawesi Tengah,
            sebesar 66 MW pada tahun 2020.
          </h6>
          <br />

          <!-- <h6>Ilustrasi Manfaat Sikllus :</h6> -->
          <center>
            <div>
              <video class="vid2" play controls loop width="300" id="myVideo">
                <source
                  src="@/assets/video/EnergiTerbarukan.mp4"
                  type="video/mp4"
                />
                Your browser does not support HTML5 video.
              </video>
              <h6>
                Sumber : Modifikasi dari
                <a
                  href="https://www.youtube.com/watch?v=q8HmRLCgDAI "
                  target="_blank"
                >
                  Youtube Student Energy</a
                >
              </h6>
            </div>
          </center>
        </CCardBody>
      </CCard>
    </CCol>
  </CRow>
</template>

<script>
export default {
  name: 'Breadcrumbs',
}
</script>
