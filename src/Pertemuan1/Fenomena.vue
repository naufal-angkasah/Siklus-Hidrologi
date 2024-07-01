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
  <Preloader v-if="isLoading" />
  <CRow>
    <CCol :xs="12">
      <CCard class="mb-4">
        <CCardHeader>
          <strong>Fenomena Hujan </strong
          ><small>(Element Daya Rusak Air) </small>
        </CCardHeader>
        <CCardBody>
          <stong>
            <h6>
              ⮚ Apa yang pertama kali terlintas dalam pikiran kita ketika
              mendengar kata air dan hujan?
            </h6>
            <h6>
              ⮚ Apakah kita sering beranggapan bahwa hujan itu sebagai suatu
              bencana? Atau sebagai rasa syukur atas nikmat Allah sebagai sang
              pencipta.
            </h6></stong
          >
          <CAccordion>
            <p>
              <strong>Dalam Al-Qur'an dijelaskan.</strong>
            </p>
            <p>
              “Telah tampak kerusakan di darat dan di laut disebabkan karena
              perbuatan tangan manusia; Allah menghendaki agar mereka merasakan
              sebagian dari (akibat) perbuatan mereka, agar mereka kembali (ke
              jalan yang benar). Katakanlah (Muhammad), “Bepergianlah di bumi
              lalu lihatlah bagaimana kesudahan orang-orang dahulu. Kebanyakan
              dari mereka adalah orang-orang yang mempersekutukan (Allah).” (QS.
              Ar-rum (30) : Ayat 41-42)
              <br />
            </p>

            <p>
              "Lalu Kami bukakan pintu-pintu langit dengan (menurunkan) air yang
              tercurah, dan Kami jadikan bumi menyemburkan mata-mata air maka
              bertemulah (air-air) itu sehingga (meluap menimbulkan) keadaan
              (bencana) yang telah ditetapkan. Dan Kami angkut dia (Nuh) ke atas
              (kapal) yang terbuat dari papan dan pasak. (al-Qamar (54) : ayat
              11-13)
            </p>
            <p>
              Dia (anaknya) menjawab, “Aku akan mencari perlindungan ke gunung
              yang dapat menghindarkan aku dari air bah!” (Nuh) berkata, “Tidak
              ada yang melindungi dari siksaan Allah pada hari ini selain Allah
              yang Maha Penyayang.” Dan gelombang menjadi penghalang antara
              keduanya; maka dia (anak itu) termasuk orang yang ditenggelamkan.
              (QS Hud (11) : ayat 43)
            </p>
            <br />
            <h6>
              ⮚ Bila kita amati, pada saat musim hujan air sangat berlimpah
              bahkan menimbulkan banjir di beberapa daerah. Sebaliknya, apabila
              musim kemarau datang banyak tempat di sekitar kita yang kekurangan
              air, kemanakah air tersebut? apakah jumlah air dari semenjak
              diciptakan oleh Tuhan YME hingga sekarang berkurang jumlahnya?
            </h6>
            <br />
            <div>
              <h5>⮚ Banjir</h5>
              <div class="d-flex justify-content-md-center">
                <video class="vid2" play loop controls id="myVideo">
                  <source src="../assets/video/Banjir.mp4" type="video/mp4" />
                  Your browser does not support HTML5 video.
                </video>
              </div>
              <center>
                <br />
                <h6>
                  Sumber :
                  <a
                    href=" https://www.youtube.com/watch?v=Ve7zncHZxvQ"
                    target="_blank"
                  >
                    Youtube KOMPASTV</a
                  >
                </h6>
              </center>
            </div>
            <br />
            <div>
              <h5>⮚ Kemarau</h5>
              <div class="d-flex justify-content-md-center">
                <video class="vid2" play loop controls id="myVideo">
                  <source src="../assets/video/Kemarau.mp4" type="video/mp4" />
                  Your browser does not support HTML5 video.
                </video>
              </div>
              <center>
                <br />
                <h6>
                  Sumber :
                  <a
                    href="  https://www.youtube.com/watch?v=UPfqP8G4aoA"
                    target="_blank"
                  >
                    Youtube Liputan6</a
                  >
                </h6>
              </center>
            </div>
            <br />
          </CAccordion>
          <strong>
            <p class="bold">
              ⮚ Mari, kita cari tahu lebih banyak tentang keistimewaan air
              melalui e-modul ini. Agar dapat membantu kita menemukan
              fakta-fakta ilmiah yang menarik seputar air dan air dijelasakan di
              dalam Al-Qur’an.
            </p>
          </strong>
        </CCardBody>
      </CCard>
    </CCol>
  </CRow>
</template>

<script>
import { ref } from 'vue'
import Preloader from '@/components/Layouts/Preloader'
export default {
  name: 'Accordion',
  components: {
    Preloader,
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
  setup() {
    const activeKey = ref(1)
    const flushActiveKey = ref(1)

    return {
      activeKey,
      flushActiveKey,
    }
  },
}
</script>
