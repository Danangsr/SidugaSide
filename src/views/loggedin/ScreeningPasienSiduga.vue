<template>
  <div id="ScreeningPasienSiduga">
    <myheader></myheader>
    <b-container>
      <b-row>
        <b-col md="12" style="margin-top: 60px; margin-bottom: 60px">
          <div class="box">
            <b-row>
              <b-col md="12">
                <h3 class="text-center m-t-0 m-b-0">
                  <strong>SCREENING PASIEN SIDUGA</strong>
                </h3>
              </b-col>
            </b-row>
            <b-row class="m-t-15">
              <b-col md="12">
                <b-alert show variant="primary" style="margin-top: 15px">
                  <div style="width: 100%; display: table">
                    <div style="display: table-row">
                      <div style="display: table-cell; width: 30%">
                        <h5>Nama</h5>
                      </div>
                      <div style="display: table-cell; width: 5%">
                        <h5>:</h5>
                      </div>
                      <div style="display: table-cell">
                        <h5>{{ pasien.nama }}</h5>
                      </div>
                    </div>

                    <div style="display: table-row">
                      <div style="display: table-cell; width: 30%">
                        <h5>Alamat</h5>
                      </div>
                      <div style="display: table-cell; width: 5%">
                        <h5>:</h5>
                      </div>
                      <div style="display: table-cell">
                        <h5>{{ pasien.alamat }}</h5>
                      </div>
                    </div>
                  </div>
                </b-alert>
              </b-col>
            </b-row>
            <b-row class="m-t-15">
              <b-col md="12">
                <b-breadcrumb>
                  <b-breadcrumb-item href="/dashboard">
                    <b-icon
                      icon="house-fill"
                      scale="1.25"
                      shift-v="1.25"
                      aria-hidden="true"
                    ></b-icon>
                    Dashboard
                  </b-breadcrumb-item>

                  <b-breadcrumb-item
                    ><router-link :to="'/screening'"
                      >Data Pasien</router-link
                    ></b-breadcrumb-item
                  >

                  <b-breadcrumb-item active
                    >Screening Pasien Siduga</b-breadcrumb-item
                  >
                </b-breadcrumb>
              </b-col>
            </b-row>

            <b-row>
              <b-col md="12">
                <div class="accordion" role="tablist">
                  <b-card no-body class="mb-1">
                    <b-card-header header-tag="header" class="p-1" role="tab">
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
                    <b-card-header header-tag="header" class="p-1" role="tab">
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
                    <b-card-header header-tag="header" class="p-1" role="tab">
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
                    <b-card-header header-tag="header" class="p-1" role="tab">
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

                <b-alert
                  show
                  variant="primary"
                  style="margin-top: 15px; margin-bottom: 0"
                >
                  <h4 class="alert-heading">
                    Skor Kuisioner Regulasi Emosi :
                    {{ nilaiPernyataan }}
                  </h4>
                </b-alert>

                <b-button
                  variant="primary"
                  class="m-t-15"
                  v-on:click="submitData"
                  >Simpan
                </b-button>
              </b-col>
            </b-row>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
import myheader from "../../components/header";

// import axios from "axios";
export default {
  name: "ScreeningPasienSiduga",
  components: {
    myheader,
  },

  data() {},
};
</script>
<style scoped>
</style>