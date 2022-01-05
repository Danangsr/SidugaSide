<template>
  <div id="login">
    <b-container class="bv-example-row">
      <b-row>
        <b-col md="4" offset-md="4">
          <div
            style="
              display: flex;
              height: 100vh;
              background-color: ;
              align-items: center;
            "
          >
            <div
              style="
                width: 100%;
                height: ;
                background-color: ;
                padding: 30px;
                background-color: rgba(0, 0, 0, 0.7);
                border-radius: 6px;
                color: #fff;
              "
            >
              <h2 class="text-center">LOGIN SIDE</h2>
              <hr />
              <b-form>
                <b-alert :show="show" :variant="variant">{{ pesan }}</b-alert>
                <b-form-group label="Username">
                  <b-form-input
                    v-model="email"
                    required
                    placeholder="Enter Username"
                  ></b-form-input>
                </b-form-group>

                <b-form-group label="Password">
                  <b-form-input
                    type="password"
                    v-model="password"
                    required
                    placeholder="Enter Password"
                  ></b-form-input>
                </b-form-group>

                <div v-if="proses">Loading...</div>
                <b-button @click="logindong" variant="primary">Login</b-button>
              </b-form>
            </div>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
// @ is an alias to /src
// import { mapState, mapGetters, mapActions } from "vuex";
import axios from "axios";
import { ip_server } from "@/ip_server";

export default {
  name: "login",
  data() {
    return {
      isLogin: false,
      email: "",
      password: "",
      show: false,
      pesan: "",
      variant: "",
      proses: false,
    };
  },

  props: {
    tujuan: String,
  },

  watch: {
    //memperhatikan state token dari vuex store
    // token(newValue, oldValue) {
    //   if (newValue != oldValue && newValue != "" && newValue != undefined) {
    //     //lempar ke halaman dashboard
    //     this.$route.query.tujuan
    //       ? this.$router.push({ path: this.$route.query.tujuan })
    //       : this.$router.push({ name: "screeningUserPasien" });
    //     this.$swal.close();
    //   }
    // },
    proses(newValue) {
      let vm = this;
      if (newValue == true) {
        this.loading();
      } else {
        vm.$swal.close();
      }
    },
  },

  // mounted:function(){
  //     console.log(this.$route.query.tujuan)
  // },

  computed: {
    // ...mapState("Login", ["token", "pesan", "proses"]),
    // ...mapGetters("Login", ["cekLogin"]),
  },

  methods: {
    // ...mapActions("Login", ["doLogin", "doLogout"]),
    logindong: async function () {
      let vm = this;
      vm.show = true;
      vm.proses = true;

      let send = await axios.post(ip_server + "pasien/login", {
        username: vm.email,
        password: vm.password,
      });

      if (send.data.token) {
        vm.show = false;
        vm.proses = false;
        localStorage.setItem("idUser", send.data.id);
        localStorage.setItem("token", send.data.token);
        vm.$router.push(
          "/screeningUserPasien/" + localStorage.getItem("idUser")
        );
      } else if (send.data.message) {
        vm.show = true;
        vm.variant = "danger";
        vm.pesan = send.data.message;
        console.log(vm.pesan);
        vm.alert = true;
        vm.proses = false;

        setTimeout(() => {
          vm.show = false;
        }, 4000);
      }
    },
    logoutdong: function () {
      this.doLogout();
      // this.isLogin =  this.cekLogin
    },
    loading() {
      let vm = this;
      vm.$swal({
        title: "Mohon Tunggu...",
        allowEscapeKey: false,
        allowOutsideClick: false,
        onOpen: () => {
          vm.$swal.showLoading();
        },
      });
    },
  },
};
</script>

<style scoped>
#login {
  background-image: url("../assets/bg.jpg");
  background-size: 100%;
  background-repeat: repeat;
  /* background-position: 100% ; */
}
</style>
