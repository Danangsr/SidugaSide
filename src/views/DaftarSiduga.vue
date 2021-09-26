<template>
  <div id="daftar-siduga">
    <b-overlay :show="show" rounded="sm">
      <b-container>
        <b-row>
          <b-col xs="12" sm="12" md="4" lg="4" offset-md="4" offset-lg="4">
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
                  <h4 class="text-center"><strong>PENDAFTARAN</strong></h4>
                </b-col>

                <b-col xs="12" sm="12" md="12" lg="12" class="mt-4">
                  <b-form>
                    <b-form-group label="Nama Lengkap">
                      <b-form-input v-model="nama" size="lg"></b-form-input>
                    </b-form-group>

                    <b-form-group label="Username">
                      <b-form-input v-model="username" size="lg"></b-form-input>
                    </b-form-group>

                    <b-form-group label="Password">
                      <b-form-input
                        v-model="password"
                        type="password"
                        size="lg"
                      ></b-form-input>
                    </b-form-group>

                    <b-button
                      @click="daftar"
                      variant="primary"
                      class="mt-3"
                      size="lg"
                      block
                      >Daftar</b-button
                    >
                  </b-form>

                  <b-alert :show="alert" variant="success"
                    >Berhasil mendaftar akun, mohon tunggu 3 detik untuk
                    otomatis melanjutkan ke halaman login</b-alert
                  >
                  <b-alert :show="alert2" variant="danger">{{ pesan }}</b-alert>
                </b-col>
              </b-row>
            </div>
          </b-col>
        </b-row>
      </b-container>
    </b-overlay>
  </div>
</template>

<script>
import Axios from "axios";
import { ip_server } from "@/ip_server";
// @ is an alias to /src
// import { mapState, mapGetters, mapActions } from 'vuex'

export default {
  name: "daftarSiduga",
  data() {
    return {
      isLogin: false,
      show: false,
      alert: false,
      alert2: false,
      nama: "",
      pesan: "",
      password: "",
      username: "",
    };
  },
  methods: {
    async daftar() {
      let vm = this;
      vm.show = true;

      let send = await Axios.post(ip_server + "user/register", {
        nama: vm.nama,
        password: vm.password,
        username: vm.username,
      });

      console.log(send);

      if (send.data.id) {
        vm.show = false;
        vm.alert = true;

        setTimeout(() => {
          vm.alert = false;
          vm.$router.push("/dashboardSiduga");
        }, 3000);
      } else if (send.data.message) {
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
#daftar-siduga {
  width: 100%;
  min-height: 100vh;
  background-image: url("../assets/bgsiduga.jpg");
  background-size: cover;
  padding: 30px 0;
}

#daftar-siduga .box-konten {
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

#daftar-siduga .box-konten h1 {
  font-size: 48px;
  font-weight: bold;
}
</style>
