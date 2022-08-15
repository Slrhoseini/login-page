<template>
  <v-app>
    <v-main>
      <v-container class="fill-height">
        <v-row align="center" justify="center">
          <div class="cont1">
            <v-img
              class="img"
              src="./assets/img2.jpeg"
              alt="Logo"
              contain
              height="360"
              width="450"
            ></v-img>
          </div>
          <v-col cols="10" sm="10" md="6" lg="6">
            <v-card elevation="3">
              <v-card-text>
                <v-form ref="form" @submit.prevent="submit">
                  <div class="inputs">
                    <p>سامانه جلوگیری از نشت اطلاعات</p>
                    <v-text-field
                      label="Username"
                      name="username"
                      prepend-inner-icon="mdi-account"
                      :rules="rules.name"
                    >
                    </v-text-field>
                    <v-text-field
                      label="Password"
                      name="password"
                      prepend-inner-icon="mdi-lock"
                      :type="showPassword ? 'text' : 'password'"
                      :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                      @click:append="showPassword = !showPassword"
                      :rules="rules.name"
                    >
                    </v-text-field>

                    <v-card-actions class="text--secondary">
                      <v-text-field
                        label="Enter the characters"
                        name="captcha"
                        :rules="rules.name"
                      >
                      </v-text-field>
                      <a href="#" style="color: #fff">
                        <v-icon color="white" size="20">mdi-reload</v-icon>
                      </a>
                      <v-img
                        class="img ml-4"
                        src="./assets/captcha.jpg"
                        alt="Logo"
                        contain
                        width="150"
                      ></v-img>
                    </v-card-actions>
                    <div class="text-center">
                      <v-btn
                        type="submit"
                        class="white--text"
                        dark
                        x-large
                        rounded
                        width="200"
                        >Login</v-btn
                      >
                    </div>
                  </div>
                </v-form>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      showPassword: false,
      rules: {
        name: [(val) => (val || "").length > 0 || "This field is required"],
      },
    };
  },
  methods: {
    resetForm() {
      this.form = Object.assign({}, this.defaultForm);
      this.$refs.form.reset();
      this.$toast.show("Hey! im here");
    },
    submit() {
      this.snackbar = true;
      this.resetForm();
    },
  },
};
</script>

// linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)),
<style>
main {
  /* background: linear-gradient(rgba(0, 0, 0, 0.1), rgba(0, 0, 0, 0.1)),
    linear-gradient(to right, #141e30, #243b55); */
  background-image: linear-gradient(rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2)),
    url("./assets/t1.jpg");
  background-size: cover;
}
.img {
  margin-right: auto;
  margin-left: auto;
}
.v-card {
  background: linear-gradient(to right, #141e30, #243b55);
}
.v-btn {
  background: linear-gradient(to right, #1cb5e0, #4286f4);
  margin-top: 10px;
}
p {
  margin-top: 10px;
  font-family: Calibri;
  font-size: 27px;
  font-weight: bold;
  text-align: center;
  margin-right: 40px;
  color: #fff;
}
.cont1 {
  opacity: 0.9;
}
.inputs {
  width: 85%;
  margin-left: auto;
  margin-right: auto;
}
</style>
