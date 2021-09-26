<template>
  <div id="login-siduga">
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
                      style="height: 180px"
                    />
                  </center>

                  <h1 class="mt-2 text-center"><strong>SIDUGA</strong></h1>
                  <h5 class="text-center">
                    Sistem Informasi<br />Dukungan Keluarga ODGJ
                  </h5>
                </b-col>

                <b-col xs="12" sm="12" md="12" lg="12" class="mt-5">
                  <h4 class="text-center"><strong>MASUK APLIKASI</strong></h4>
                </b-col>

                <b-col xs="12" sm="12" md="12" lg="12" class="mt-3">
                  <b-form-group>
                    <b-form-input
                      required
                      v-model="username"
                      placeholder="Masukkan Username"
                      size="lg"
                    ></b-form-input>
                  </b-form-group>

                  <b-form-group>
                    <b-form-input
                      type="password"
                      v-model="password"
                      required
                      placeholder="Masukkan Password"
                      size="lg"
                      @keypress.enter="login"
                    ></b-form-input>
                  </b-form-group>

                  <b-button
                    variant="primary"
                    class="mt-3"
                    size="lg"
                    block
                    @click="login"
                    >Login</b-button
                  >

                  <b-alert
                    style="position: absolute; right: 0; left: 0"
                    fade
                    :show="alert"
                    variant="danger"
                    >{{ pesan }}</b-alert
                  >
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
// import axios from "axios";

export default {
  name: "LoginSiduga",
  data() {
    return {
      isLogin: false,
      username: "",
      password: "",
      alert: false,
      show: false,
      pesan: "",
    };
  },
  methods: {
    async login() {
      let vm = this;
      vm.show = true;

      let send = await Axios.post(ip_server + "pasien/login", {
        username: vm.username,
        password: vm.password,
      });

      if (send.data.token) {
        vm.show = false;
        localStorage.setItem("idUser", send.data.id);
        localStorage.setItem("token", send.data.token);
        vm.$router.push("/dashboardSiduga");
      } else if (send.data.message) {
        vm.show = false;
        vm.pesan = send.data.message;
        vm.alert = true;

        setTimeout(() => {
          vm.alert = false;
        }, 3000);
      }
    },
  },
};
</script>

<style scoped>
#login-siduga {
  width: 100%;
  min-height: 100vh;
  background-image: url("../assets/bgsiduga.jpg");
  background-size: cover;
  padding: 30px 0;
}

#login-siduga .box-konten {
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

#login-siduga .box-konten h1 {
  font-size: 48px;
  font-weight: bold;
}
</style>
