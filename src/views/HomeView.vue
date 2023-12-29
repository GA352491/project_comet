<template>
  <div class="row">
    <div class="tu-login-left col-6">
      <strong class="pb-5 mb-3">
        <a href="index-2.html">
          <img
            src="https://ecomett.com.au/assetsWeb/images/login/logo_white.png"
            alt="images"
        /></a>
      </strong>
      <figure>
        <img
          src="https://ecomett.com.au/assetsWeb/images/login/img-01.png"
          alt="images"
        />
      </figure>
      <div class="tu-login-left_title" style="color: white">
        <h2>Yes! we’re making progress</h2>
        <span>every minute &amp; every second</span>
      </div>
    </div>

    <div class="col-6 mt-5 pt-5">
      <div class="d-flex justify-content-center">
        <div class="tu-login-right_title">
          <h2 style="color: #602eaf">Welcome!</h2>
          <h3>It’s really nice to see you</h3>
        </div>
      </div>

      <form
        class="px-5 p-5 mt-5 w-75"
        style="float: none; margin: auto"
        @submit.prevent="submitForm"
      >
        <div class="mb-3">
          <input
            type="text"
            class="form-control"
            id="Username"
            placeholder="Full Name"
            aria-label="Username"
            v-model="fullname"
          />
        </div>
        <div class="mb-3">
          <input
            type="email"
            class="form-control"
            id="exampleInputEmail1"
            placeholder="Your email address"
            v-model="email"
          />
        </div>
        <div class="mb-3">
          <input
            type="password"
            class="form-control"
            placeholder="Enter Password"
            id="exampleInputPassword1"
            v-model="password"
          />
        </div>
        <div class="mb-3">
          <input
            type="password"
            class="form-control"
            placeholder="Re-Enter Password"
            id="exampleInputPassword2"
            v-model="password2"
          />
        </div>
        <div class="mb-3">
          <div class="input-group mb-3">
            <div class="form-group">
              <div class="tu-select" style="margin: auto">
                <select
                  class="form-control valid"
                  name="user_timezone"
                  required=""
                  aria-required="true"
                  aria-invalid="false"
                  v-model="timezone"
                >
                  <option value="">Select Timezone</option>
                  <option value="AWST">Australian Western Standard Time</option>
                  <option value="ACST">Australian Central Standard Time</option>
                  <option value="AEST">Australian Eastern Standard Time</option>
                </select>
              </div>
              <p class="text-danger"></p>
            </div>
          </div>
        </div>
        <div class="mb-3">
          <div class="form-group">
            <div class="tu-check tu-signup-check">
              <input type="checkbox" id="expcheck2" name="TnC" value="1" />
              <label for="expcheck2"
                ><span
                  >I have read and agree to all
                  <a href="javascript:void(0);">Terms &amp; conditions</a></span
                ></label
              >
            </div>
            <p class="text-danger"></p>
          </div>
        </div>
        <div class="mb-3">
          <div class="form-group">
            <div class="form-group">
              <button
                type="submit"
                class="btn btn tu-primbtn-lg w-100"
                style="background-color: #602eaf; color: white"
              >
                <span>Join now</span><i class="icon icon-arrow-right"></i>
              </button>
            </div>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<style scoped>
.tu-login-left {
  width: 50%;
  display: flex;
  padding: 50px 30px;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  background-color: #0a0f26;
}
.tu-login-right {
  width: 50%;
  display: flex;
  padding: 50px 30px;
  align-items: center;
  flex-direction: column;
  justify-content: center;
}
.tu-login-right_title {
  text-align: center;
}
</style>
<script>
import axios from "axios";

export default {
  name: "signup",
  data() {
    return {
      fullname: "",
      email: "",
      password: "",
      password2: "",
      timezone: "",
      errors: [],
    };
  },
  methods: {
    submitForm() {
      console.log(
        "this is signup form ",
        this.email,
        this.fullname,
        this.password,
        this.password2
      );
      this.errors = [];
      if (this.fullname == "") {
        this.errors.push("the username is missing");
      }
      if (this.password != this.password2) {
        this.errors.push("please check password");
      }

      console.log(this.errors.length, "errors");
      if (!this.errors.length) {
        console.log("data enter ");
        const formData = {
          email: this.email,
          fullname: this.fullname,
          password: this.password,
          password2: this.password2,
          timezone: this.timezone,
          user_type: "tutor",
        };
        console.log("formdata", formData);
        axios
          .post("http://127.0.0.1:8000/api/signup/", formData)
          .then((response) => {
            if (response.status == 201) {
              const data = response.data;
              console.log("data", data);
              this.$router.push("about/");
            } else {
              alert(response.data);
            }
          })
          .catch((error) => {
            if (error.response) {
              for (const property in error.response.data) {
                this.errors.push(
                  `${property}: ${error.response.data[property]}`
                );
              }
              console.log(JSON.stringify(error.response.data));
            } else if (error.message) {
              this.errors.push("Something went wrong. Please try again");

              console.log(JSON.stringify(error));
            }
          });
      }
    },
  },
};
</script>
