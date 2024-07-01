<!-- eslint-disable prettier/prettier -->

<template>
  <Navbar />
  <!-- <div>{{ kognitif[0]}}</div> -->
  <div v-if="kognitif[questionIndex]">
    <div class="container p-2 overflow-auto">
      <div class="card">
        <div class="row p-5 card-body">
          <section class="radio-section col-sm">
            <div class="px-2">
              <div class="radio-list" style="font-size: 10px">
                <center>
                  <img
                    v-if="kognitif[questionIndex].gambar !== null"
                    :src="
                      require(
                        `../../assets/img/ujian/${kognitif[questionIndex].gambar}`,
                      )
                    "
                    alt=""
                    width="400"
                  />
                </center>
                <br />
                <div v-for="(k, index) in kognitif" :key="k.id" class="">
                  <div v-show="index === questionIndex" class="question">
                    <div class="">
                      <p style="font-size: 20px">
                        {{ index + 1 }}. {{ k.pertanyaan }}
                      </p>
                      <ul>
                        <li
                          class="radio-item form-check py-2"
                          v-for="response in k.opsi"
                          :key="response.id"
                        >
                          <input
                            @click="emitSelectedOption(index + 1, response.id)"
                            :id="response.id + k.pertanyaan"
                            type="radio"
                            v-bind:value="response.isi"
                            v-bind:name="response.isi"
                            v-model="userResponses[index]"
                            class="form-check-input"
                          />
                          <label
                            style="font-size: 20px"
                            class="form-check-label justify-content-start"
                            :for="response.id + k.pertanyaan"
                            >{{ response.id }}. {{ response.isi }}
                          </label>
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>
          <div
            v-if="questionIndex === kognitif.length - 1"
            class="d-flex justify-content-sm-end pt-5"
          >
            <!-- <button type="button" class="next round" >&#8250;</button> -->
            <!-- <h1>klik ke PPL</h1> -->
            <CButton
              class="btn-lg"
              :class="choose ? '' : 'disabled'"
              color="success"
              @click="
                () => {
                  ;(visibleScrollableDemo = true), nextModal()
                }
              "
              >Selesai &#8250;</CButton
            >

            <!-- <button class="btn btn-success" @click="addData">Selesai &#8250;</button> -->
          </div>
          <div v-else class="d-flex justify-content-sm-end pt-5">
            <button
              class="btn btn-lg btn-info"
              :class="choose ? '' : 'disabled'"
              @click="nextQuestion"
              style="font-size: 20px"
            >
              Berikutnya &#8250;
            </button>
          </div>
        </div>
      </div>
    </div>
    <!-- modal -->
    <CModal
      scrollable
      size="lg"
      :visible="visibleScrollableDemo"
      @close="
        () => {
          visibleScrollableDemo = false
        }
      "
      aria-labelledby="ScrollingLongContentExampleLabel2"
    >
      <CModalHeader>
        <CModalTitle id="ScrollingLongContentExampleLabel2"
          >Peringatan</CModalTitle
        >
      </CModalHeader>
      <CModalBody>
        <div class="accordion-body">
          <p>Lanjut Aspek Perilaku Ekoliterasi?</p>
          <p>10 soal</p>
        </div>
        <p>⮚ Jika halaman mengalami kejanggalan segera refresh</p>
        <br />
        <div class="modal-footer">
          <button type="button" class="btn btn-danger" data-bs-dismiss="modal">
            Tidak
          </button>
          <button type="submit" @click="addData" class="btn btn-primary">
            Mulai
          </button>
        </div>
      </CModalBody>
    </CModal>
  </div>

  <!-- <div v-if="jawaban">
    {{ jawaban }}
  </div> -->
</template>
<!-- eslint-disable prettier/prettier -->

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Averia+Serif+Libre:wght@300;400;700&display=swap');

ul {
  list-style-type: none;
}

body {
  font-family: 'Averia Serif Libre', cursive;
  background-color: rgb(19, 18, 21);
  color: #ffffff;
}

h1 {
  margin-bottom: 20px;
}

.radio-item label {
  display: block;
  padding: 0px 10px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 12px;
  font-weight: 400;
  position: relative;
}

.radio-item label:after,
.radio-item label:before {
  content: '';
  position: absolute;
  border-radius: 50%;
}

.radio-item label:after {
  height: 19px;
  width: 19px;

  left: 19px;
}

.radio-item label:before {
  height: 20px;
  width: 20px;
  left: 21px;
  top: calc(50%-5px);
  transform: scale(5);
  opacity: 0;
  visibility: hidden;
  transition: 0.4s ease-in-out 0s;
}

.radio-item [type='radio']:checked ~ label::before {
  opacity: 1;
  visibility: visible;
  transform: scale(1);
}
</style>
<!-- eslint-disable prettier/prettier -->

<script>
import Navbar from '@/components/Pretest/Navbar.vue'
import axios from 'axios'
import { uuid } from 'vue-uuid'
// import { ref } from "vue";
// import { uuid } from 'vue-uuid'
var kognitif = [
  {
    id: '1',
    gambar: null,
    pertanyaan:
      'Air memegang peranan penting dalam kehidupan. Keberadaan air di muka bumi tersebar dalam berbagai bentuk. Salah satu kajian geografi didalamnya mempelajari tentang lapisan air, baik air tawar, air asin, air beku dan air di tingkat lapisan udara yang lebih rendah dalam istilah objek material geografi disebut sebagai …',
    opsi: [
      {
        id: 'a',
        isi: 'Geosfer',
      },
      {
        id: 'b',
        isi: 'Atmosfer',
      },
      {
        id: 'c',
        isi: 'Hidrosfer',
      },
      {
        id: 'd',
        isi: 'Litosfer',
      },
    ],
    jawaban: 'c',
  },
  // {
  //   id: '2',
  //   gambar: null,
  //   pertanyaan:
  //     'Lingkaran peredaran air di bumi yang mempunyai jumlah tetap dan senantiasa bergerak disebut...',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: 'Siklus hidrosfer',
  //     },
  //     {
  //       id: 'b',
  //       isi: 'Siklus hidrografi',
  //     },
  //     {
  //       id: 'c',
  //       isi: 'Siklus geohidrologi',
  //     },
  //     {
  //       id: 'd',
  //       isi: 'Siklus hidrologi',
  //     },
  //   ],
  //   jawaban: 'd',
  // },
  // {
  //   id: '3',
  //   gambar: 'no3.jpg',
  //   pertanyaan:
  //     'Berdasarkan gambar diatas, nomor 2 menunjukkan proses …. Yang terjadi dalam siklus hidrologi.',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: 'Evapotranspirasi : penguapan dari air permukaan dan tumbuhan.',
  //     },
  //     {
  //       id: 'b',
  //       isi: 'Kondensasi: Semua bentuk hujan dari atmosfer ke bumi yang meliputi air, salju, dan es.',
  //     },
  //     {
  //       id: 'c',
  //       isi: 'Presipitasi:  berubahnya awan menjadi titik-titik air atau salju.',
  //     },
  //     {
  //       id: 'd',
  //       isi: 'Infiltrasi:  Perembesan atau pergerakan air ke dalam tanah melalui pori-pori tanah.',
  //     },
  //   ],
  //   jawaban: 'a',
  // },
  // {
  //   id: '4',
  //   gambar: 'no4.jpg',
  //   pertanyaan:
  //     'Berdasarkan gambar diatas ini, jenis siklus air yang terjadi adalah…',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: 'Siklus sedang',
  //     },
  //     {
  //       id: 'b',
  //       isi: 'Siklus pendek',
  //     },
  //     {
  //       id: 'c',
  //       isi: 'Siklus panjang',
  //     },
  //     {
  //       id: 'd',
  //       isi: 'Siklus temporer',
  //     },
  //   ],
  //   jawaban: 'a',
  // },
  {
    id: '2',
    gambar: 'no5.jpg',
    pertanyaan:
      'Berdasarkan gambar diatas, Urutan proses siklus hidrologi yang benar adalah?',
    opsi: [
      {
        id: 'a',
        isi: '1, 2, 3, dan 4',
      },
      {
        id: 'b',
        isi: '1, 4, 3, dan 2',
      },
      {
        id: 'c',
        isi: '2, 3, 4, dan 1',
      },
      {
        id: 'd',
        isi: '3, 4, 1, dan 2',
      },
    ],
    jawaban: 'd',
  },
  {
    id: '3',
    gambar: null,
    pertanyaan:
      'Berikut ini yang merupakan pasangan yang tepat mengenai jenis proses yang terjadi dalam daur air dengan keterangannya yang tepat adalah...',
    opsi: [
      {
        id: 'a',
        isi: 'Evaporasi : Proses perubahan wujud uap air menjadi air akibat adanya pendinginan.',
      },
      {
        id: 'b',
        isi: 'Kondensasi: Semua bentuk hujan dari atmosfer ke bumi yang meliputi air, salju, dan es.',
      },
      {
        id: 'c',
        isi: 'Presipitasi:  berubahnya awan menjadi titik-titik air atau salju.',
      },
      {
        id: 'd',
        isi: 'Infiltrasi:  Perembesan atau pergerakan air ke dalam tanah melalui pori-pori tanah.',
      },
    ],
    jawaban: 'd',
  },
  // {
  //   id: '7',
  //   gambar: null,
  //   pertanyaan:
  //     'Faktor-faktor yang mempengaruhi infiltrasi adalah...',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: 'Tingkat resistensi batuan dan luas permukaan tanah',
  //     },
  //     {
  //       id: 'b',
  //       isi: 'Luas permukaan tanah dan besarnya suhu udara',
  //     },
  //     {
  //       id: 'c',
  //       isi: 'Kemiringan permukaan tanah dan vegetasi',
  //     },
  //     {
  //       id: 'd',
  //       isi: 'Permukaan tanah dan vegetasi',
  //     },
  //   ],
  //   jawaban: 'a',
  // },
  {
    id: '4',
    gambar: null,
    pertanyaan:
      'Berikut ini yang merupakan faktor alami penyebab masalah lingkungan hidup akibat dari fenomena siklus hidrologi adalah…',
    opsi: [
      {
        id: 'a',
        isi: 'Banjir',
      },
      {
        id: 'b',
        isi: 'Limbah industri',
      },
      {
        id: 'c',
        isi: 'Menebang pohon',
      },
      {
        id: 'd',
        isi: 'Membuang sampah di sungai',
      },
    ],
    jawaban: 'a',
  },
  // {
  //   id: '9',
  //   gambar: null,
  //   pertanyaan:
  //     'Saat matahari bersinar terang di atas sungai, panasnya memicu penguapan air dari permukaan sungai. Air ini berubah menjadi uap air dan naik ke atmosfer. Apakah volume air sungai akan berkurang karena proses evaporasi?',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: 'Ya, karena uap air belum tentu menjadi hujan',
  //     },
  //     {
  //       id: 'b',
  //       isi: 'Ya, karena uap air akan menjadi air tanah.',
  //     },
  //     {
  //       id: 'c',
  //       isi: 'Tidak, karena air yang menguap menjadi uap air hanya sedikit',
  //     },
  //     {
  //       id: 'd',
  //       isi: 'Tidak, karena uap air tersebut akan kembali ke sungai',
  //     },
  //   ],
  //   jawaban: 'd',
  // },
  {
    id: '5',
    gambar: null,
    pertanyaan:
      'Daur air adalah perubahan yang terjadi pada air secara berulang dalam suatu pola tertentu. Air di sungai, danau, rawa, laut, serta hasil transpirasi tumbuhan akan menguap membentuk awan. Awan tersebut adalah hasil…',
    opsi: [
      {
        id: 'a',
        isi: 'Penyerapan titik-titik air yang jatuh kembali ke tanah',
      },
      {
        id: 'b',
        isi: 'Titik-titik air jatuh menuju permukaan Bumi dalam bentuk hujan atau salju',
      },
      {
        id: 'c',
        isi: 'Uap air di atmosfer mengalami pengembunan',
      },
      {
        id: 'd',
        isi: 'Air dipermukaan Bumi mengalami penguapan olah panas',
      },
    ],
    jawaban: 'c',
  },
  {
    id: '6',
    gambar: 'no.11.png',
    pertanyaan:
      'Peran dan fungsi hutan dalam menjaga fungsi siklus air agar kestabilan lingkungan tetap terjaga ditunjukan pada nomor...',
    opsi: [
      {
        id: 'a',
        isi: '1,2, dan 3',
      },
      {
        id: 'b',
        isi: '1,3, dan 4',
      },
      {
        id: 'c',
        isi: '2,3, dan 5',
      },
      {
        id: 'd',
        isi: '2,4, dan 5',
      },
    ],
    jawaban: 'a',
  },
  {
    id: '7',
    gambar: null,
    pertanyaan:
      'Salah satu fungsi hutan adalah untuk menjaga cadangan dan kualitas air di daerah sekitarnya. Jika terjadi deforestasi di suatu kawasan hutan tersebut, maka fenomena apa yang akan terjadi berkaitan dengan fungsi hutan tersebut…',
    opsi: [
      {
        id: 'a',
        isi: 'Kepunahan flora dan fauna secara masal',
      },
      {
        id: 'b',
        isi: 'Berkurangnya cadangan air di musim hujan',
      },
      {
        id: 'c',
        isi: 'Berpotensi terjadi bencana banjir saat musim hujan',
      },
      {
        id: 'd',
        isi: 'Air tanah di sekitar hutan menjadi tercemar',
      },
    ],
    jawaban: 'b',
  },
  {
    id: '8',
    gambar: null,
    pertanyaan:
      'Kegiatan reboisasi dengan menanami pohon pada hutan gundul mempengaruhi proses siklus hidrologi dan berdampak positif bagi pencegahan banjir. Fungsi pepohonan hutan dalam siklus hidrologi adalah....',
    opsi: [
      {
        id: 'a',
        isi: 'Mempercepat aliran permukaan',
      },
      {
        id: 'b',
        isi: 'Mengurangi curah hujan',
      },
      {
        id: 'c',
        isi: 'Meningkatkan infiltrasi',
      },
      {
        id: 'd',
        isi: 'Mengurangi penguapan',
      },
    ],
    jawaban: 'c',
  },
  // {
  //   id: '14',
  //   gambar: 'no.14.png',
  //   pertanyaan:
  //     'Tindakan manusia terhadap hutan yang membantu menjaga siklus air adalah ...',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: '1 dan 3',
  //     },
  //     {
  //       id: 'b',
  //       isi: '2 dan 3',
  //     },
  //     {
  //       id: 'c',
  //       isi: '3 dan 4',
  //     },
  //     {
  //       id: 'd',
  //       isi: '1 dan 4',
  //     },
  //   ],
  //   jawaban: 'a',
  // },
  {
    id: '9',
    gambar: null,
    pertanyaan:
      'Untuk mencegah terjadinya tanah longsor, pemerintah mendorong penanaman 1001 pohon di sekitar area yang rawan. Tujuan dari langkah tersebut adalah….',
    opsi: [
      {
        id: 'a',
        isi: 'Meningkatkan retensi air dalam tanah dengan penanaman pohon.',
      },
      {
        id: 'b',
        isi: 'Mengurangi erosi tanah dan melindungi lapisan tanah dengan penanaman pohon.',
      },
      {
        id: 'c',
        isi: 'Adanya banyak pohon menciptakan lingkungan yang lebih hijau.',
      },
      {
        id: 'd',
        isi: 'Meningkatkan kadar oksigen di udara dan menjaga kandungan air tanah.',
      },
    ],
    jawaban: 'b',
  },
  // {
  //   id: '16',
  //   gambar: null,
  //   pertanyaan:
  //     'Akhir-akhir ini di daerah Aceh terjadi hujan yang mengakibatkan banjir. Ini disebabkan oleh banyak jalan yang sudah di aspal. Pengaruh jalan yang diaspal terhadap banjir adalah …',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: 'Aspal menyebabkan air hujan tidak bisa langsung menyerap ke dalam permukaan tanah',
  //     },
  //     {
  //       id: 'b',
  //       isi: 'Aspal menyebabkan proses penyerapan air hujan kedalam tanah menjadi lama',
  //     },
  //     {
  //       id: 'c',
  //       isi: 'Aspal menutup saluran irigasi',
  //     },
  //     {
  //       id: 'd',
  //       isi: 'Aspal membunuh tanaman yang ada di sekitarnya',
  //     },
  //   ],
  //   jawaban: 'a',
  // },
  {
    id: '10',
    gambar: null,
    pertanyaan:
      'Ayah menyiram tanaman dengan air bekas cucian beras, kegiatan yang dilakukan ayah lakukan tersebut berpengaruh terhadap kelestarian sumber air. Berikut pernyataan yang dapat menjelaskan hubungan antara kegiatan ayah terhadap kelestarian sumber air adalah....',
    opsi: [
      {
        id: 'a',
        isi: 'Ayah mempraktikkan penghematan air',
      },
      {
        id: 'b',
        isi: 'Ayah membuang-buang air secara tidak bijaksana.',
      },
      {
        id: 'c',
        isi: 'Ayah mencemari tanah',
      },
      {
        id: 'd',
        isi: 'Tanaman mawar mati karena tidak tepatnya pemberian air oleh ayah.',
      },
    ],
    jawaban: 'a',
  },
  // {
  //   id: '18',
  //   gambar: null,
  //   pertanyaan:
  //     'Air merupakan unsur yang sangat penting bagi kelangsungan hidup manusia. Apa yang harus dilakukan untuk menjaga kelestarian alam yang berdampak pada tersedianya air bersih, kecuali....',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: 'Mengurangi penggunaan air',
  //     },
  //     {
  //       id: 'b',
  //       isi: 'Menebang pohon di hutan',
  //     },
  //     {
  //       id: 'c',
  //       isi: 'Mencemari lingkungan ',
  //     },
  //     {
  //       id: 'd',
  //       isi: 'Membuang limbah pabrik sembarangan',
  //     },
  //   ],
  //   jawaban: 'b',
  // },
  {
    id: '11',
    gambar: null,
    pertanyaan:
      'Di perkotaan, halaman rumah masyarakat cenderung ditutupi dengan paving atau material beton, sehingga menyebabkan air hujan sulit diserap oleh tanah, yang dapat menyebabkan genangan air dan bahkan banjir saat hujan. Salah satu usaha yang dapat dilakukan untuk mencegah banjir dalam kondisi tersebut adalah....',
    opsi: [
      {
        id: 'a',
        isi: 'Menutup got agar airnya tidak meluber.',
      },
      {
        id: 'b',
        isi: 'Memperlebar daerah aliran sungai.',
      },
      {
        id: 'c',
        isi: 'Meningkatkan pembuatan saluran air (got-got).',
      },
      {
        id: 'd',
        isi: 'Membuat lubang-lubang biopori.',
      },
    ],
    jawaban: 'd',
  },
  // {
  //   id: '20',
  //   gambar: null,
  //   pertanyaan:
  //     'urangnya air di bumi dapat menyebabkan banyaknya hewan yang mengalami dehidrasi dan tumbuhan yang tidak tumbuhan dengan baik. Kesimpulan yang didapat dari peristiwa diatas adalah …',
  //   opsi: [
  //     {
  //       id: 'a',
  //       isi: 'Menyadari pentingnya dan bermanfaatnya proses siklus agar dapat menjaga siklus air',
  //     },
  //     {
  //       id: 'b',
  //       isi: 'Mencari sumber air dengan melakukan penggalian',
  //     },
  //     {
  //       id: 'c',
  //       isi: 'Membiarkan saja dengan memanfaatkan yang ada untuk kepentingan sendiri',
  //     },
  //     {
  //       id: 'd',
  //       isi: 'Tetap menggunakan air secara berlebihan',
  //     },
  //   ],
  //   jawaban: 'a',
  // },
]
export default {
  name: 'Appkognitif',
  components: {
    Navbar,
  },
  data() {
    return {
      // active: false,
      time: 0,
      kognitif: kognitif,
      questionIndex: 0,
      jawaban: [],
      user: null,
      temp: [],
      userResponses: Array(kognitif.length).fill(false),
      visibleScrollableDemo: false,
      show: true,
      choose: false,
    }
  },

  methods: {
    setKognitif(data) {
      this.kognitif = data
    },

    emitSelectedOption(no, jawaban) {
      this.temp = []
      this.temp.push([no, jawaban])
      this.choose = true
    },
    nextQuestion() {
      // this.temp.push([no, jawaban])
      this.jawaban.push(this.temp) //formatnya no soal dan jawaban yang di pilih user
      this.questionIndex++
      this.temp = []
      this.choose = false
    },
    nextModal() {
      // this.temp.push([no, jawaban])
      this.jawaban.push(this.temp) //formatnya no soal dan jawaban yang di pilih user
      // this.questionIndex++
      this.temp = []
      this.choose = false
    },
    async addData() {
      const datas = {
        id: uuid.v1(),
        id_user: JSON.parse(localStorage.getItem('id_user')),
        jawabanKognitif: this.jawaban,
        isKognitif: true,
      }
      console.log(datas)

      await axios
        .post(
          `https://api-kakerol-git-main-fathinafifs-projects.vercel.app/api/v1/jawabanKognitif/`,
          datas,
        )
        .then((response) => {
          console.log('berhasil:', response.data)
        })
        .catch((error) => {
          return console.log('Gagal : ', error)
        })
      this.$router.push({ path: '/ppl-pretest' })
    },
  },
  mounted() {
    //reload sekali
    if (localStorage.getItem('reloaded')) {
      // The page was just reloaded. Clear the value from local storage
      // so that it will reload the next time this page is visited.
      localStorage.removeItem('reloaded')
    } else {
      // Set a flag so that we know not to reload the page twice.
      localStorage.setItem('reloaded', '1')
      location.reload()
    }
  },
}
</script>
