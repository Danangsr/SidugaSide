<template>
  <div>
    <myheaderSiduga></myheaderSiduga>
    <section id="screening-siduga">
      <b-container>
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
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga menunjukan bahwa kita sebagai keluarga terdekat peduli terhadap penderita"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga menghormati setiap keputusan yang diungkapkan oleh penderita"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Kelurga menyarankan penderita agar tetap menjalin hubungan sosial dengan orang lain"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga mengamati perilaku penderita ketika terdapat kemajuan dalam perawatan"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
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
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Kelurga menyarankan penderita untuk rutin control/berobat ke pelayanan Kesehatan terdekat"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga mengingatkan hal-hal yang harus dihindari yang dapat membuat penderita terserang penyakit"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga mengingatkan penderita untuk tetap menjaga kesehatan"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga mencari informasi tentang masalah kesehatan yang dialami penderita"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
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
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga meluangkan waktu untuk menemani penderita agar tetap menjada kesehatan"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga menyediakan trasnportasi untuk mempermudah dalam perawatan kesehatan"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga memberikan uang kepada penderita"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga mengantar kemana penderita akan pergi"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
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
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga memberikan perhatian dengan menciptakan suasana lingkungan rumah yang aman"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga memberikan kepercayaan kepada penderita dalam proses keperawatan"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga mendengarkan curhatan hari penderita ketika sedih"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>

                                <b-form-group
                                  label="Keluarga membertikan kasih sayang kepada penderita dalam proses perawatan"
                                >
                                  <b-form-select
                                    :options="options"
                                    size="lg"
                                  ></b-form-select>
                                </b-form-group>
                              </b-col>
                            </b-row>
                          </b-card-body>
                        </b-collapse>
                      </b-card>
                    </div>

                    <b-button variant="primary" size="lg" class="mt-3"
                      >Simpan</b-button
                    >
                  </b-form>
                </b-col>
              </b-row>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
// import { mapState, mapGetters, mapActions } from 'vuex'
import myheaderSiduga from "../components/headerSiduga";

export default {
  name: "daftarSiduga",
  components: {
    myheaderSiduga,
  },
  data() {
    return {
      isLogin: false,
      options: [
        { value: "4", text: "Selalu" },
        { value: "3", text: "Sering" },
        { value: "2", text: "Kadang-Kadang" },
        { value: "1", text: "Tidak Pernah" },
      ],
    };
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
