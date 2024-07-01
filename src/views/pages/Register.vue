<!-- eslint-disable prettier/prettier -->

<template>
  <Preloader v-if="isLoading" />
  <div class="begregis ptb-100 bounceInDown">
    <!-- <template> -->
    <div class="container-fluid">
      <div class="row mt-lg-n10 mt-md-n11 mt-n10 justify-content-center">
        <div class="col-xl-8 col-lg-5 col-md-7 mx-auto">
          <div class="card0 z-index-0">
            <div class="card-header text-center pt-4">
              <h4 class="roboto-regular">REGISTER</h4>
            </div>
            <div class="card-body" style="font-size: 1.2em">
              <b-form
                class="p-3"
                @submit="onSubmit"
                v-if="show"
              >
                <!-- nama -->
                <b-row class="my-1">
                  <b-col sm="3">
                    <label for="type-name"><code>Nama</code> :</label>
                  </b-col>
                  <b-col sm="9">
                    <b-form-input
                      trim
                      id="type-name"
                      aria-describedby="input-live-help input-live-feedback"
                      :state="errors.includes('name_required') ? false : none"
                      v-model="form.name"
                      placeholder="Masukkan Nama"
                    ></b-form-input>
                    <!-- {{errors.includes('name_required') ? false : true}} -->
                    <b-form-invalid-feedback id="type-name">
                      Nama Perlu ditambahkan
                    </b-form-invalid-feedback>
                  </b-col>
                </b-row>
                <!-- email -->
                <b-row class="my-2">
                  <b-col sm="3">
                    <label for="type-email"><code>Email</code> :</label>
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
                        errors.includes('Email_exist')
                          ? false
                          : none
                      "
                      placeholder="Masukkan Email"
                    ></b-form-input>

                    <b-form-invalid-feedback
                      v-if="errors.includes('Email_exist')"
                      id="type-email"
                    >
                      Email Sudah Terdaftar
                    </b-form-invalid-feedback>
                    <b-form-invalid-feedback
                      v-if="errors.includes('email_required')"
                      id="type-email"
                    >
                      Email Perlu ditambahkan
                    </b-form-invalid-feedback>
                  </b-col>
                </b-row>
                <b-row class="my-2">
                  <b-col sm="3">
                    <label for="type-kelas"><code>Nama Sekolah</code> :</label>
                  </b-col>
                  <b-col sm="9">
                    <b-form-input
                      trim
                      id="type-kelas"
                      v-model="form.kelas"
                      type="text"
                      aria-describedby="input-live-help input-live-feedback"
                      :state="errors.includes('kelas_required') ? false : none"
                      placeholder="Contoh: SMA / MA 1"
                    ></b-form-input>
                    <b-form-invalid-feedback id="type-kelas">
                      Nama Sekolah Perlu ditambahkan
                    </b-form-invalid-feedback>
                  </b-col>
                </b-row>
                <b-row class="my-2">
                  <b-col sm="3">
                    <label for="type-pelajaran"
                      ><code>Mata Pelajaran</code> :</label
                    >
                  </b-col>
                  <b-col sm="9">
                    <b-form-input
                      trim
                      id="type-pelajaran"
                      v-model="form.pelajaran"
                      type="text"
                      aria-describedby="input-live-help input-live-feedback"
                      :state="
                        errors.includes('pelajaran_required') ? false : none
                      "
                      placeholder="Contoh: Geografi"
                    ></b-form-input>
                    <b-form-invalid-feedback id="type-pelajaran">
                      Pelajaran Perlu ditambahkan
                    </b-form-invalid-feedback>
                  </b-col>
                </b-row>
                <!-- password -->
                <b-row class="my-2">
                  <b-col sm="3">
                    <label for="type-password"><code>Password</code> :</label>
                  </b-col>
                  <b-col sm="9">
                    <b-form-input
                      id="type-password"
                      v-model="form.password"
                      type="password"
                      aria-describedby="input-live-help input-live-feedback"
                      :state="
                        errors.includes('password_required') ? false : none
                      "
                      placeholder="Masukkan Password"
                    ></b-form-input>
                    <b-form-invalid-feedback id="type-password">
                      Password Perlu ditambahkan
                    </b-form-invalid-feedback>
                  </b-col>
                </b-row>
                <b-row class="my-2">
                  <b-col sm="3">
                    <label for="type-password-confirm"
                      ><code>Konfirmasi Password</code> :</label
                    >
                  </b-col>
                  <b-col sm="9">
                    <b-form-input
                      id="type-password-confirm"
                      v-model="form.passwordConfirm"
                      type="password"
                      placeholder="Masukkan Konfirmasi Password"
                      aria-describedby="input-live-help input-live-feedback"
                      :state="
                        errors.includes('passwordConfirm_required') ||
                        form.password !== form.passwordConfirm
                          ? false
                          : none
                      "
                    ></b-form-input>

                    <b-form-invalid-feedback
                      v-show="errors.includes('passwordConfirm_not_same')"
                      id="type-password-confirm"
                    >
                      Konfirmasi Password yang anda Masukkan Salah.
                    </b-form-invalid-feedback>
                    <b-form-invalid-feedback
                      v-show="errors.includes('passwordConfirm_required')"
                      id="type-password-confirm"
                    >
                      Masukkan Konfirmasi Password
                    </b-form-invalid-feedback>
                  </b-col>
                </b-row>
                <!-- semester -->
                <b-row class="my-2">
                  <b-col sm="3">
                    <label for="input-group-3"><code>Kelas</code> :</label>
                  </b-col>
                  <b-col sm="9">
                    <b-form-group
                      class="is-invalid"
                      id="input-group-3"
                      label-for="input-3"
                    >
                      <b-form-select
                        id="input-3"
                        v-model="form.semester"
                        :options="semesters"
                      ></b-form-select>
                    </b-form-group>
                    <div
                      v-show="errors.includes('semester_required')"
                      class="invalid-feedback"
                    >
                      Masukkan Kelas
                    </div>
                    <!-- <b-form-invalid-feedback id="input-3">
                      Masukkan Semester
                    </b-form-invalid-feedback> -->
                  </b-col>
                </b-row>

                <b-button class="mx-2" type="submit" variant="primary"
                  >Submit</b-button
                >
                <!-- <b-button type="reset" variant="danger">Reset</b-button> -->
              </b-form>
              <div class="px-1 pt-2 text-center card-footer px-lg-2">
                <p class="mx-auto mb-4 text-sm">
                  Sudah Punya Akun?
                  <a
                    href="/login"
                    class="text-gradient font-weight-bold"
                    >Masuk</a
                  >
                </p>
              </div>
              <!-- <b-card class="mt-3" header="Form Data Result">
                <pre class="m-0">{{ form }}</pre>
                {{ datas }}
              </b-card> -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import { uuid } from 'vue-uuid'
import Preloader from '@/components/Layouts/Preloader'
export default {
  name: 'Register',
  components: {
    Preloader,
  },
  data() {
    return {
      isLoading: true,
      datas: [],
      errors: [],
      form: {
        id: uuid.v1(),
        email: '',
        name: '',
        pelajaran: '',
        semester: null,
        kelas: '',
        password: '',
        passwordConfirm: '',
        isPretest: false,
        isPosttest: false,
        isAdmin: false,
      },
      semesters: [
        { text: 'Pilih Salah satu', value: null },
        { text: 'Kelas X (Satu) / Semester Ganjil', value: 1 },
        { text: 'Kelas X (Satu) / Semester Genap', value: 2 },
      ],
      show: true,
    }
  },

  _methods: {
    setData(data) {
      //untuk menyimpan data registrasi
      this.datas = data.users //soalnya bentuk array di kembalikannya
    },
    async onSubmit(event) {
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
      // console.log(this.datas)
      //cek apakah ada di dalam email database
      var index = this.datas.findIndex((o) => o.email === this.form.email)
      // this.datas.findIndex((o) => console.log(o.email === this.form.email))
      console.log('index:', index)
      if (index > -1) {
        // this.datas.findIndex((o) => console.log(o.email === this.form.email))
        this.errors.push('Email_exist')
      }
      //cek apakah password tidak sama
      if (
        this.form.password != this.form.passwordConfirm &&
        !this.errors.includes('passwordConfirm' + '_required')
      ) {
        this.errors.push('passwordConfirm' + '_not_same')
      }
      if (this.errors.length === 0) {
        let data = this.form
        delete data.passwordConfirm
        console.log('ini data:', data)
        await axios
          .post(
            'https://api-kakerol-git-main-fathinafifs-projects.vercel.app/api/v1/user',
            data,
          )
          // .post(http://localhost:5000/api/v1/user/, data)
          .then((response) => {
            console.log('berhasil:', response.data)
          })
          .catch((error) => {
            return console.log('Gagal : ', error)
          })
        this.$router.push({ path: '/login' })
        // alert(JSON.stringify(data)) //tampilkan notif toast atau navbar bahw aberhasil di daftrkan
      }
    },
    onReset(event) {
      event.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.name = ''
      this.form.semester = null
      this.form.password = ''
      this.form.passwordConfirm = ''
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    },
  },
  get methods_1() {
    return this._methods
  },
  set methods_1(value) {
    this._methods = value
  },
  get methods() {
    return this._methods
  },
  set methods(value) {
    this._methods = value
  },
  mounted() {
    setTimeout(() => {
      this.isLoading = false
    }, 2000)
    // Make a request for a user with a given ID
    axios
      // .get(http://localhost:5000/api/v1/user)
      .get(
        'https://api-kakerol-git-main-fathinafifs-projects.vercel.app/api/v1/user',
      )
      .then((response) => this.setData(response.data))
      .catch((error) => {
        console.log('Gagal : ', error)
      })
    // console.log(this.datas.users)
  },
}
</script>
