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
          <strong>Penutup</strong>
        </CCardHeader>
        <CCardBody>
          <p>
            Dari penjelasan tersebut, ternyata didalam Alquran juga sudah
            dijelaskan bahwasannya, hujan merupakan rahmat dan rizki yang
            diturunkan kepada hamba-hambanya. Yaitu dalam surat:
          </p>
          <ul style="list-style-type: none">
            <li><strong>⮚ Surat al-furqan ayat : 48</strong></li>
            <p style="text-align: center">
              وَهُوَ الَّذِيْٓ اَرْسَلَ الرِّيٰحَ بُشْرًاۢ بَيْنَ يَدَيْ
              رَحْمَتِهٖۚ وَاَنْزَلْنَا مِنَ السَّمَاۤءِ مَاۤءً طَهُوْرًا ۙ |48
            </p>
            <P
              >Dialah yang meniupkan angin (sebagai) pembawa kabar gembira
              sebelum kedatangan rahmat-Nya (hujan). Kami turunkan dari langit
              air yang sangat suci.</P
            >
            <li><strong>⮚ Surat Ar-Ruum ayat : 48</strong></li>
            <p style="text-align: center">
              ٱللَّهُ ٱلَّذِى يُرْسِلُ ٱلرِّيَٰحَ فَتُثِيرُ سَحَابًا
              فَيَبْسُطُهُۥ فِى ٱلسَّمَآءِ كَيْفَ يَشَآءُ وَيَجْعَلُهُۥ
              كِسَفًا فَتَرَى ٱلْوَدْقَ يَخْرُجُ مِنْ خِلَٰلِهِۦ ۖ فَإِذَآ
              أَصَابَ بِهِۦ مَن يَشَآءُ مِنْ عِبَادِهِۦٓ إِذَا هُمْ
              يَسْتَبْشِرُونَ |48
            </p>
            <p>
              Allah Yang Mahasuci yang mengendalikan angin dan menggerakkannya,
              lalu angin itu menggerakkan awan dan Dia membentangkannya di
              langit dengan sekehendak-Nya baik sedikit maupun banyak dan
              menjadikannya gumpalan-gumpalan, maka engkau lihat -wahai orang
              yang melihat- hujan turun dari sela-selanya.
            </p>
          </ul>
        </CCardBody>
        <CCardBody>
          ⮚ Siklus air di bumi merupakan suatu fenomena yang menunjukkan
          kemahabesaran Allah dengan segala kuasa-Nya dalam mengatur alam
          semesta ini. Sebab jumlah air bumi yang tidak pernah berkurangatau
          bertambah sepanjang abad ini dialirkan ke berbagai penjuru di dunia
          untuk memenuhi kebutuhan makhluk-Nya. <br /><br />
          ⮚ Siklus hidrologi merupakan proses daur ulang untuk membersihkan air
          dari berbagai kotoran dan sesuatu yang mencemarinya. Proses tersebut
          juga berfungsi untuk menjaga keseimbangan temperatur bumi.
        </CCardBody>
      </CCard>
      <CCard class="mb-4"
        ><CCardHeader><strong>Penjelasan Alqur'an</strong> </CCardHeader
        ><CCardBody
          >Allah, Dialah yang mengirim angin, lalu angin itu menggerakkan awan
          dan Allah membentangkannya di langit menurut yang dikehendaki-Nya, dan
          menjadikannya bergumpal-gumpal; lalu kamu lihat hujan ke luar dari
          celah-celahnya, maka apabila hujan itu turun mengenai hamba-hamba-Nya
          yang dikehendaki-Nya tiba-tiba mereka menjadi gembira.
          <strong>(Q.S Ar-Rūm (30) : ayat 48)</strong><br /><br />
          Dalam
          <CButton
            color="link"
            v-c-tooltip="{
              content:
                'Mauliddin, A. I. (2018). Telaah kritis makna hujan dalam Alquran. Al-Quds: Jurnal Studi Alquran Dan Hadis, 2(1), 87-102.',
              placement: 'top',
            }"
            >kitabnya</CButton
          >
          Ibnu Katsir menjelaskan tentang Ar-Rum (30) : 48, “..... dan dengan
          turunnya hujan tersebut hamba-hamba-Nya menjadi gembira karena
          kebutuhan mereka terhadapnya”
        </CCardBody>
        <!-- <p>Ilustrasi Infiltrasi</p> -->
        <center>
          <div>
            <video class="vid2" play controls loop width="100" id="myVideo">
              <source
                src="@/assets/video/Anakbermainhujan.mp4"
                type="video/mp4"
              />
              Your browser does not support HTML5 video.
            </video>
            <h6>
              Sumber : Modifikasi
              <a
                href="https://www.youtube.com/watch?v=Sh_Aox-t-uE"
                target="_blank"
              >
                Youtube Nurul Fajri
              </a>
            </h6>
          </div>
        </center>
      </CCard>
    </CCol>
  </CRow>
</template>

<script>
export default {
  name: 'Placeholders',
}
</script>
