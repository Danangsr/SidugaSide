<template>
  <div>
    <b-overlay :show="show" rounded="sm">
      <myheaderSiduga></myheaderSiduga>
      <section id="biodata-siduga">
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
                    <h4 class="text-center"><strong>BIODATA PASIEN</strong></h4>
                  </b-col>
                </b-row>

                <b-row class="mt-4">
                  <b-col xs="12" sm="12" md="12" lg="12">
                    <b-form>
                      <b-form-group label="Nama Pasien">
                        <b-form-input
                          v-model="data.nama"
                          placeholder=""
                          size="lg"
                        ></b-form-input>
                      </b-form-group>

                      <!-- <b-form-group label="Username">
                      <b-form-input
                        v-model="data.username"
                        placeholder=""
                        size="lg"
                      ></b-form-input>
                    </b-form-group>

                    <b-form-group label="password">
                      <b-form-input
                        v-model="data.password"
                        placeholder=""
                        size="lg"
                      ></b-form-input>
                    </b-form-group> -->

                      <b-form-group label="Tanggal Lahir">
                        <!-- <b-form-datepicker
                        v-model="data.tanggalLahir"
                        size="lg"
                      ></b-form-datepicker> -->
                        <date-picker
                          v-model="data.tanggalLahir"
                          valueType="format"
                          style="width: 100%"
                          required
                        ></date-picker>
                      </b-form-group>

                      <b-form-group label="Alamat">
                        <b-form-input
                          v-model="data.alamat"
                          placeholder=""
                          size="lg"
                        ></b-form-input>
                      </b-form-group>

                      <b-form-group label="Pendidikan">
                        <b-form-input
                          v-model="data.pendidikanPasien"
                          placeholder=""
                          size="lg"
                        ></b-form-input>
                      </b-form-group>

                      <b-form-group label="Lama Perawatan">
                        <b-form-input
                          v-model="data.lamaPerawatan"
                          placeholder=""
                          type="number"
                          size="lg"
                        ></b-form-input>
                      </b-form-group>

                      <b-form-group label="Penanggung Jawab Pasien">
                        <b-form-input
                          v-model="data.penanggungJawabPasien"
                          placeholder=""
                          size="lg"
                        ></b-form-input>
                      </b-form-group>

                      <b-button variant="primary" size="lg" @click="edit"
                        >Simpan</b-button
                      >
                    </b-form>

                    <b-alert
                      style="position: absolute; right: 0; left: 0"
                      fade
                      :show="alert"
                      variant="success"
                      >Profil berhasil diubah</b-alert
                    >
                    <b-alert
                      style="position: absolute; right: 0; left: 0"
                      fade
                      :show="alert2"
                      variant="danger"
                      >{{ pesan }}</b-alert
                    >
                  </b-col>
                </b-row>
              </div>
            </b-col>
          </b-row>
        </b-container>
      </section>
    </b-overlay>
  </div>
</template>

<script>
import Axios from "axios";
import { ip_server } from "@/ip_server";
// @ is an alias to /src
// import { mapState, mapGetters, mapActions } from 'vuex'
import myheaderSiduga from "../components/headerSiduga";
import moment from "moment";
moment.locale("id");
import DatePicker from "vue2-datepicker";
import "vue2-datepicker/index.css";

export default {
  name: "BiodataSiduga",
  components: {
    myheaderSiduga,
    DatePicker,
  },
  data() {
    return {
      show: false,
      alert: false,
      alert2: false,
      pesan: "",
      data: {},
      moment,
    };
  },
  mounted() {
    let vm = this;
    Axios.get(
      ip_server + "pasien/details/" + Number(localStorage.getItem("idUser")),
      {
        headers: {
          accesstoken: localStorage.getItem("token"),
        },
      }
    ).then((res) => {
      if (res.data.respon) {
        vm.data = res.data.respon[0];
      }
    });
  },
  methods: {
    async edit() {
      let vm = this;
      vm.show = true;
      let send = await Axios.patch(
        ip_server + "pasien/" + Number(localStorage.getItem("idUser")),
        {
          nama: vm.data.nama,
          alamat: vm.data.alamat,
          tanggalLahir: vm.data.tanggalLahir,
          pendidikanPasien: vm.data.pendidikanPasien,
          lamaPerawatan: Number(vm.data.lamaPerawatan),
          penanggungJawabPasien: vm.data.penanggungJawabPasien,
          // username: vm.data.username,
          // password: vm.data.password,
        },
        {
          headers: {
            accesstoken: localStorage.getItem("token"),
          },
        }
      );
      if (send.data[1]) {
        vm.show = false;
        vm.alert = true;

        setTimeout(() => {
          vm.alert = false;
        }, 3000);
      } else {
        vm.show = false;
        vm.alert2 = true;
        vm.pesan = send.data.message;

        setTimeout(() => {
          vm.alert2 = false;
        }, 3000);
      }
    },
  },
};
</script>

<style scoped>
#biodata-siduga {
  width: 100%;
  min-height: 100vh;
  background-image: url("../assets/bgsiduga.jpg");
  background-size: cover;
  padding: 30px 0;
}

#biodata-siduga .box-konten {
  width: 100%;
  min-height: 100vh;
  /* display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column; */
}

#biodata-siduga .box-konten h1 {
  /* font-size: 48px; */
  font-weight: bold;
}
</style>
