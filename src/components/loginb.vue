<!-- eslint-disable prettier/prettier -->
<template>
  <div>
    <audio play autoplay>
      <source src="@/assets/selamat.mp3" type="audio/mpeg" />
      Your browser does not support the audio element.
    </audio>
    <div class="begron ptb-100 rubberBand">
      <div class="container-fluid">
        <div class="row align-items-center">
          <div class="col-lg-8 col-md-12">
            <div class="overview-content">
              <div
                class="card6 tracking-in-expand-fwd-top"
                style="padding-top: 10px"
              >
                <center>
                  <div>
                    <p1 style="color: white">SELAMAT DATANG</p1>
                  </div>
                  <p2
                    style="color: white; text-shadow: rgb(0, 0, 0) 2px 2px 2px"
                    >Siswa-siswi terbaik bangsa,</p2
                  >
                </center>
                <center>
                  <table
                    style="
                      th,
                      td {
                        padding: 15px;
                        text-align: left;
                      }
                      padding-left: 50px;
                    "
                  >
                    <tr>
                      <td style="padding: 1ch; padding-top: 35px">
                        <p3 style="text-shadow: rgb(0, 0, 0) 2px 2px 2px"
                          >di</p3
                        >
                      </td>
                      <td>
                        <h11
                          style="
                            color: white;
                            text-shadow: rgb(0, 0, 0) 2px 2px 2px;
                          "
                          >E-MODUL</h11
                        >
                      </td>
                    </tr>
                  </table>
                </center>
                <center>
                  <h11
                    style="color: white; text-shadow: rgb(0, 0, 0) 2px 2px 2px"
                    >SIKLUS HIDROLOGI</h11
                  >
                  <br />
                  <p2
                    style="color: white; text-shadow: rgb(0, 0, 0) 2px 2px 2px"
                    >Terintegrasi Ayat-Ayat Al Quran</p2
                  >
                  <h6
                    style="color: white; text-shadow: rgb(0, 0, 0) 2px 2px 2px"
                  >
                    Muhammad Khairul - Class of 2022<br />Master Pendidikan
                    Geografi<br />Universitas Pendidikan Indonesia
                  </h6>
                </center>
              </div>
            </div>
          </div>
          <div class="col-lg-4 col-md-12">
            <div
              class="row align-items-center overview-content"
              style="padding-right: 10px; padding-left: 10px"
            >
              <div class="card0 z-index-0">
                <div class="card-header text-center pt-4">
                  <br />
                  <h4 class="roboto-regular">LOGIN</h4>
                </div>
                <div class="card-body p-3" style="font-size: 1.2em">
                  <b-form
                    class="p-3"
                    @submit="onSubmit"
                    @reset="onReset"
                    v-if="show"
                  >
                    <!-- email -->
                    <b-row class="my-2">
                      <b-col sm="3">
                        <label for="`type-email`"><code>Email</code>:</label>
                      </b-col>
                      <b-col sm="9">
                        <b-form-input
                          trim
                          id="type-email"
                          v-model="form.email"
                          type="email"
                          aria-describedby="input-live-help input-live-feedback"
                          :state="
                            errors.includes('email_required') ||
                            errors.includes('email_wrong')
                              ? false
                              : none
                          "
                          placeholder="Masukkan Email.."
                        ></b-form-input>

                        <!-- <b-form-invalid-feedback v-if="errors.includes('Email_exist')" id="type-email">
                        Email Sudah Terdaftar
                        </b-form-invalid-feedback>  -->
                        <b-form-invalid-feedback
                          v-if="errors.includes('email_required')"
                          id="type-email"
                        >
                          Email Perlu ditambahkan
                        </b-form-invalid-feedback>
                        <b-form-invalid-feedback
                          v-if="errors.includes('email_wrong')"
                          id="type-password"
                        >
                          Email ini tidak terdaftar
                        </b-form-invalid-feedback>
                      </b-col>
                    </b-row>
                    <!-- password -->
                    <b-row class="my-2">
                      <b-col sm="3">
                        <label for="type-password"
                          ><code>Password</code>:</label
                        >
                      </b-col>
                      <b-col sm="9">
                        <b-form-input
                          id="type-password"
                          v-model="form.password"
                          type="password"
                          aria-describedby="input-live-help input-live-feedback"
                          :state="
                            errors.includes('password_required') ||
                            errors.includes('password_wrong')
                              ? false
                              : none
                          "
                          placeholder="Masukkan Password.."
                        ></b-form-input>
                        <b-form-invalid-feedback
                          v-if="errors.includes('password_required')"
                          id="type-password"
                        >
                          Password Perlu ditambahkan
                        </b-form-invalid-feedback>
                        <b-form-invalid-feedback
                          v-if="errors.includes('password_wrong')"
                          id="type-password"
                        >
                          Password yang ada masukkan salah
                        </b-form-invalid-feedback>
                      </b-col>
                    </b-row>
                    <br />
                    <CButton
                      color="primary"
                      @click="
                        () => {
                          visibleScrollableDemo = true
                        }
                      "
                      >Login</CButton
                    >
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
                          >Petunjuk E-Module</CModalTitle
                        >
                      </CModalHeader>
                      <CModalBody>
                        <p>
                          Berikut adalah langkah-langkah yang lebih detail untuk
                          menggunakan e-modul tentang siklus hidrologi:
                        </p>
                        <div class="accordion-body">
                          <ol class="bold">
                            <li>
                              <strong>Registrasi : </strong><br />
                              Buka e-modul dan temukan opsi registrasi. Isi
                              informasi yang diperlukan seperti nama, email, dan
                              informasi lain yang diminta. Ikuti instruksi untuk
                              menyelesaikan proses registrasi.
                            </li>
                            <br />
                            <li>
                              <strong>Pretest :</strong><br />
                              Setelah registrasi selesai, cari dan pilih opsi
                              untuk mengerjakan pretest. Kerjakan pretest sesuai
                              dengan petunjuk yang diberikan. Pastikan untuk
                              memahami pertanyaan dan memberikan jawaban dengan
                              cermat.
                            </li>
                            <br />
                            <li>
                              <strong>Halaman Utama :</strong><br />Setelah
                              selesai pretest, kembali ke halaman awal. Baca
                              informasi yang ditampilkan di halaman utama secara
                              menyeluruh. Luangkan waktu untuk membaca berbagai
                              poin yang tersedia dengan seksama.
                            </li>
                            <br />
                            <li>
                              <strong>Kegiatan Inti (Pertemuan I) :</strong
                              ><br />Pilih opsi menuju ke kegiatan inti atau
                              pertemuan I. Pada pertemuan I, cari dan klik
                              tombol "Mulai" untuk memulai. Anda akan diarahkan
                              ke materi tentang siklus hidrologi yang
                              terintegrasi dengan ayat-ayat Alquran. Pelajari
                              materi tersebut dengan seksama dan pahami
                              keterkaitannya dengan konten Alquran yang
                              disajikan.
                            </li>
                            <br />
                            <li>
                              <strong>Aktifitas Siswa :</strong><br />Setelah
                              mengikuti materi tentang siklus hydrology
                              berintegrasi Klik pada opsi aktifitas siswa dan
                              lakukan aktivitas siswa yang ada pada modul.
                            </li>
                            <br />
                            <li>
                              <strong>Pengayaan :<br /></strong>Setelah
                              melakukan aktifitas siswa. Silahkan mengisi
                              laporan pengamatan Kembali ke halaman utama dan
                              masuk ke dalam materi pengayaan. Silahkan membaca
                              materi-materi yang tersedia uantuk menambah
                              berbagai informasi tambahan tentang siklus air.
                            </li>
                            <br />
                            <li>
                              <strong>Refleksi :</strong> <br />Pada menu
                              relfeksi, mari merenungkan kembali apa yang sudah
                              kita pelajari dan Bersama-sama menyimpulkan
                              pembelajaran
                            </li>
                            <br />
                            <li>
                              <strong>Post Test :</strong><br />Setelah
                              melakukan serangkain kegiatan pada menu “kegiatan
                              Inti”. Kemudian, Silahkan mengerjakan Pretest.
                              Setelah mengerjakan Post Tes. Maka selesai sudah
                              pertemuan kita pada hari ini.
                            </li>
                            <br />
                            <p>
                              Dengan mengikuti langkah-langkah ini secara rinci,
                              Anda akan dapat menggunakan e-modul tentang siklus
                              hidrologi terintegrasi ayat-ayat Al-Quran dengan
                              lebih efektif dan memaksimalkan manfaatnya.
                            </p>
                          </ol>
                        </div>
                        <b-button class="mx-2" type="submit" variant="primary"
                          >Login</b-button
                        >
                      </CModalBody>
                    </CModal>

                    <!-- <b-button type="reset" variant="danger">Reset</b-button> -->
                  </b-form>
                  <div class="px-1 pt-2 text-center card-footer px-lg-2">
                    <p class="mx-auto mb-4 text-sm">
                      Tidak Punya Akun?
                      <a href="/register" class="text-gradient font-weight-bold"
                        >Daftar</a
                      >
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="col-lg-12 col-md-12">
            <div class="overview-content">
              <div class="card6" style="padding-top: 10px">
                <center>
                  <p4 style="text-shadow: rgb(0, 0, 0) 2px 2px 2px"
                    >Temukan materi yang menarik dan bermanfaat tentang siklus
                    air ini. Selamat belajar dan mari eksplorasi pengetahuan
                    bersama!</p4
                  >
                </center>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<!-- eslint-disable prettier/prettier -->
<script>
import axios from 'axios'

// import { uuid } from 'vue-uuid'
// import { useRouter } from 'vue-router'

// const router = useRouter()
// const route = useRoute()

export default {
  name: 'Loginb',
  components: {},
  data() {
    return {
      visibleScrollableDemo: false,
      datas: [],
      errors: [],
      form: {
        email: '',
        password: '',
      },
      show: true,
    }
  },

  methods: {
    setData(data) {
      //untuk menyimpan data registrasi
      this.datas = data.users
    },
    onSubmit(event) {
      event.preventDefault()
      this.errors = []
      //cara validasi kata yang kosong
      Object.entries(this.form).forEach(([key, value]) => {
        //cek apakah setiap value ada di dalam database
        try {
          if (value === '' || value.length === 0 || value === null) {
            this.errors.push(key + '_required')
          }
        } catch (err) {
          this.errors.push(key + '_required')
        }
      })
      //cek apakah ada di dalam email database return ke halaman overview dn jangan lupa buat session dengan local storages untuk middleware

      if (
        !this.datas.find((o) => o.email === this.form.email) &&
        this.form.email !== ''
      ) {
        this.errors.push('email_wrong')
      }
      if (
        this.datas.find(
          (o) =>
            o.email === this.form.email && o.password !== this.form.password,
        )
      ) {
        this.errors.push('password_wrong')
      }
      //jika tidak ada error
      if (this.errors.length === 0) {
        let user = this.datas.find((o) => o.email === this.form.email)
        localStorage.setItem('isLogin', true)

        //kita coba set false dulu nnti diganti
        localStorage.setItem('isPretest', user.isPretest)
        localStorage.setItem('isPosttest', user.isPosttest)
        localStorage.setItem('user', JSON.stringify(user.name))
        localStorage.setItem('id_user', JSON.stringify(user.id))
        if (user.isAdmin) {
          localStorage.setItem('isAdmin', user.isAdmin)
          this.$router.push({ path: '/admin' })
        }
        this.$router.push({ path: '/overview' })
      }
    },
    onReset(event) {
      event.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.password = ''
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    },
  },
  mounted() {
    if (localStorage.getItem('reloaded')) {
      // The page was just reloaded. Clear the value from local storage
      // so that it will reload the next time this page is visited.
      localStorage.removeItem('reloaded')
    } else {
      // Set a flag so that we know not to reload the page twice.
      localStorage.setItem('reloaded', '1')
      location.reload()
    }
    // Make a request for a user with a given ID
    // alert('ini pop up yang isinya aturan modul')
    axios
      .get(
        `https://api-kakerol-git-main-fathinafifs-projects.vercel.app/api/v1/user`,
      )
      .then((response) => this.setData(response.data))
      .catch((error) => console.log('Gagal : ', error))
  },
}
</script>
