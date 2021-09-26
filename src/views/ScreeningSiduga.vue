<template>
  <div>
    <myheaderSiduga></myheaderSiduga>
    <section id="screening-siduga">
      <b-container>
        <b-overlay :show="show" rounded="sm">
          <b-row>
            <b-col xs="12" sm="12" md="12" lg="12">
              <div class="box-konten">
                <b-row>
                  <b-col xs="12" sm="12" md="12" lg="12">
                    <center>
                      <img
                        src="../assets/logosiduga.png"
                        alt=""
                        style="height: 150px"
                      />
                    </center>

                    <h1 class="mt-2 text-center"><strong>SIDUGA</strong></h1>
                    <h5 class="text-center">
                      Sistem Informasi<br />Dukungan Keluarga ODGJ
                    </h5>
                  </b-col>

                  <b-col xs="12" sm="12" md="12" lg="12" class="mt-5">
                    <h4 class="text-center">
                      <strong>SCREENING DUKUNGAN KELUARGA</strong>
                    </h4>
                  </b-col>
                </b-row>

                <b-row class="mt-4">
                  <b-col xs="12" sm="12" md="12" lg="12">
                    <b-form>
                      <div class="accordion" role="tablist">
                        <b-card no-body class="mb-1">
                          <b-card-header
                            header-tag="header"
                            class="p-1"
                            role="tab"
                          >
                            <b-button
                              block
                              v-b-toggle.accordion-1
                              variant="primary"
                              size="lg"
                              >Dukungan Penilaian</b-button
                            >
                          </b-card-header>
                          <b-collapse
                            id="accordion-1"
                            visible
                            accordion="my-accordion"
                            role="tabpanel"
                          >
                            <b-card-body>
                              <b-row>
                                <b-col xs="12" sm="12" md="12" lg="12">
                                  <b-form-group
                                    label="Keluarga membimbing penderita agar tetap menjada kondisi kesehatan"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal1"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga menunjukan bahwa kita sebagai keluarga terdekat peduli terhadap penderita"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal2"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga menghormati setiap keputusan yang diungkapkan oleh penderita"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal3"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Kelurga menyarankan penderita agar tetap menjalin hubungan sosial dengan orang lain"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal4"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga mengamati perilaku penderita ketika terdapat kemajuan dalam perawatan"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal5"
                                    ></b-form-select>
                                  </b-form-group>
                                </b-col>
                              </b-row>
                            </b-card-body>
                          </b-collapse>
                        </b-card>

                        <b-card no-body class="mb-1">
                          <b-card-header
                            header-tag="header"
                            class="p-1"
                            role="tab"
                          >
                            <b-button
                              block
                              v-b-toggle.accordion-2
                              variant="primary"
                              size="lg"
                              >Dukungan Informasional</b-button
                            >
                          </b-card-header>
                          <b-collapse
                            id="accordion-2"
                            accordion="my-accordion"
                            role="tabpanel"
                          >
                            <b-card-body>
                              <b-row>
                                <b-col xs="12" sm="12" md="12" lg="12">
                                  <b-form-group
                                    label="Keluarga senantiasa memberikan informasi perawatan diri yang benar"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal6"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Kelurga menyarankan penderita untuk rutin control/berobat ke pelayanan Kesehatan terdekat"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal7"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga mengingatkan hal-hal yang harus dihindari yang dapat membuat penderita terserang penyakit"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal8"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga mengingatkan penderita untuk tetap menjaga kesehatan"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal9"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga mencari informasi tentang masalah kesehatan yang dialami penderita"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal10"
                                    ></b-form-select>
                                  </b-form-group>
                                </b-col>
                              </b-row>
                            </b-card-body>
                          </b-collapse>
                        </b-card>

                        <b-card no-body class="mb-1">
                          <b-card-header
                            header-tag="header"
                            class="p-1"
                            role="tab"
                          >
                            <b-button
                              block
                              v-b-toggle.accordion-3
                              variant="primary"
                              size="lg"
                              >Dukungan Instrumental</b-button
                            >
                          </b-card-header>
                          <b-collapse
                            id="accordion-3"
                            accordion="my-accordion"
                            role="tabpanel"
                          >
                            <b-card-body>
                              <b-row>
                                <b-col xs="12" sm="12" md="12" lg="12">
                                  <b-form-group
                                    label="Keluarga memberi fasilitas (alar mandi, makan) yang diperlukan untuk melakukan aktivitas sehari-hari dalam proses perawatan"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal11"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga meluangkan waktu untuk menemani penderita agar tetap menjada kesehatan"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal12"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga menyediakan trasnportasi untuk mempermudah dalam perawatan kesehatan"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal13"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga memberikan uang kepada penderita"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal14"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga mengantar kemana penderita akan pergi"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal15"
                                    ></b-form-select>
                                  </b-form-group>
                                </b-col>
                              </b-row>
                            </b-card-body>
                          </b-collapse>
                        </b-card>

                        <b-card no-body class="mb-1">
                          <b-card-header
                            header-tag="header"
                            class="p-1"
                            role="tab"
                          >
                            <b-button
                              block
                              v-b-toggle.accordion-4
                              variant="primary"
                              size="lg"
                              >Dukungan Emosi</b-button
                            >
                          </b-card-header>
                          <b-collapse
                            id="accordion-4"
                            accordion="my-accordion"
                            role="tabpanel"
                          >
                            <b-card-body>
                              <b-row>
                                <b-col xs="12" sm="12" md="12" lg="12">
                                  <b-form-group
                                    label="Keluarga senantiasa memberikan pujian yang positif bagi penderita"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal16"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga memberikan perhatian dengan menciptakan suasana lingkungan rumah yang aman"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal17"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga memberikan kepercayaan kepada penderita dalam proses keperawatan"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal18"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga mendengarkan curhatan hari penderita ketika sedih"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal19"
                                    ></b-form-select>
                                  </b-form-group>

                                  <b-form-group
                                    label="Keluarga membertikan kasih sayang kepada penderita dalam proses perawatan"
                                  >
                                    <b-form-select
                                      :options="options"
                                      size="lg"
                                      v-model="soal20"
                                    ></b-form-select>
                                  </b-form-group>
                                </b-col>
                              </b-row>
                            </b-card-body>
                          </b-collapse>
                        </b-card>
                      </div>

                      <b-button
                        @click="kirim"
                        variant="primary"
                        size="lg"
                        class="mt-3"
                        >Simpan</b-button
                      >
                    </b-form>

                    <b-alert :show="alert" variant="success"
                      >Data screening berhasil disimpan!</b-alert
                    >
                    <b-alert :show="alert2" variant="danger"
                      >Terjadi kesalahan pada server</b-alert
                    >
                  </b-col>
                </b-row>
              </div>
            </b-col>
          </b-row>
        </b-overlay>
      </b-container>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
// import { mapState, mapGetters, mapActions } from 'vuex'
import myheaderSiduga from "../components/headerSiduga";
import axios from "axios";
import { ip_server } from "@/ip_server";

export default {
  name: "daftarSiduga",
  components: {
    myheaderSiduga,
  },
  data() {
    return {
      isLogin: false,
      options: [
        { value: 4, text: "Selalu" },
        { value: 3, text: "Sering" },
        { value: 2, text: "Kadang-Kadang" },
        { value: 1, text: "Tidak Pernah" },
      ],
      soal1: 0,
      soal2: 0,
      soal3: 0,
      soal4: 0,
      soal5: 0,
      soal6: 0,
      soal7: 0,
      soal8: 0,
      soal9: 0,
      soal10: 0,
      soal11: 0,
      soal12: 0,
      soal13: 0,
      soal14: 0,
      soal15: 0,
      soal16: 0,
      soal17: 0,
      soal18: 0,
      soal19: 0,
      soal20: 0,
      show: false,
      alert: false,
      alert2: false,
    };
  },
  mounted() {
    this.getData();
  },
  methods: {
    kirim() {
      let vm = this;
      vm.show = true;
      let token = localStorage.getItem("token");

      axios
        .post(
          ip_server + "poolODGJ/registerUpdate",
          {
            soal1: vm.soal1,
            soal2: vm.soal2,
            soal3: vm.soal3,
            soal4: vm.soal4,
            soal5: vm.soal5,
            soal6: vm.soal6,
            soal7: vm.soal7,
            soal8: vm.soal8,
            soal9: vm.soal9,
            soal10: vm.soal10,
            soal11: vm.soal11,
            soal12: vm.soal12,
            soal13: vm.soal13,
            soal14: vm.soal14,
            soal15: vm.soal15,
            soal16: vm.soal16,
            soal17: vm.soal17,
            soal18: vm.soal18,
            soal19: vm.soal19,
            soal20: vm.soal20,
          },
          {
            headers: {
              accesstoken: token,
            },
          }
        )
        .then(() => {
          vm.getData();
          vm.show = false;
          vm.alert = true;

          setTimeout(() => {
            vm.alert = false;
          }, 3000);
        })
        .catch((err) => {
          vm.alert2 = true;
          console.log(err);
        });
    },

    getData() {
      let vm = this;
      vm.show = true;
      axios
        .get(
          ip_server +
            "poolODGJ/listByPasienId/" +
            Number(localStorage.getItem("idUser")),
          {
            headers: {
              accesstoken: localStorage.getItem("token"),
            },
          }
        )
        .then((res) => {
          vm.soal1 = res.data.data[0].soal1;
          vm.soal2 = res.data.data[0].soal2;
          vm.soal3 = res.data.data[0].soal3;
          vm.soal4 = res.data.data[0].soal4;
          vm.soal5 = res.data.data[0].soal5;
          vm.soal6 = res.data.data[0].soal6;
          vm.soal7 = res.data.data[0].soal7;
          vm.soal8 = res.data.data[0].soal8;
          vm.soal9 = res.data.data[0].soal9;
          vm.soal10 = res.data.data[0].soal10;
          vm.soal11 = res.data.data[0].soal11;
          vm.soal12 = res.data.data[0].soal12;
          vm.soal13 = res.data.data[0].soal13;
          vm.soal14 = res.data.data[0].soal14;
          vm.soal15 = res.data.data[0].soal15;
          vm.soal16 = res.data.data[0].soal16;
          vm.soal17 = res.data.data[0].soal17;
          vm.soal18 = res.data.data[0].soal18;
          vm.soal19 = res.data.data[0].soal19;
          vm.soal20 = res.data.data[0].soal20;
          vm.show = false;
        });
    },
  },
};
</script>

<style scoped>
#screening-siduga {
  width: 100%;
  min-height: 100vh;
  background-image: url("../assets/bgsiduga.jpg");
  background-size: cover;
  padding: 30px 0;
}

#screening-siduga .box-konten {
  width: 100%;
  min-height: 100vh;
  /* display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column; */
}

#screening-siduga .box-konten h1 {
  /* font-size: 48px; */
  font-weight: bold;
}
</style>
