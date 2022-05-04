<template>
  <div class="container">
    <div v-if="show_alert" class="alert alert-success" role="alert">
      Text Copied To Clipboard
    </div>
    <div
      style="user-select: none"
      class="page-content page-container"
      id="page-content"
    >
      <div class="padding">
        <div class="row container d-flex justify-content-center">
          <div class="col-xl-8 col-md-12">
            <div class="card user-card-full">
              <div class="row m-l-0 m-r-0">
                <div
                  :class="[
                    gender == 'female'
                      ? 'col-sm-4 bg-c-lite-pink user-profile'
                      : 'col-sm-4 bg-c-lite-blue user-profile',
                  ]"
                >
                  <div class="card-block text-center text-white">
                    <div class="m-b-25">
                      <img
                        :src="picture"
                        class="img-radius"
                        alt="User-Profile-Image"
                      />
                    </div>
                    <h6 @dblclick="copy(name)" class="f-w-600">
                      {{ name }}
                    </h6>
                    <p @dblclick="copy_date(dob)">{{ age }} years old</p>
                    <div class="filters">
                      <div class="tw-toggle">
                        <input
                          type="radio"
                          name="toggle"
                          v-model="lookup_gender"
                          value="female"
                        />
                        <label class="toggle toggle-yes"
                          ><i class="fa fa-venus"></i
                        ></label>
                        <input
                          checked
                          type="radio"
                          name="toggle"
                          v-model="lookup_gender"
                          value="random"
                        />
                        <label class="toggle toggle-yes"
                          ><i class="fa fa-random"></i
                        ></label>
                        <input
                          type="radio"
                          name="toggle"
                          v-model="lookup_gender"
                          value="male"
                        />
                        <label class="toggle toggle-yes"
                          ><i class="fa fa-mars"></i
                        ></label>
                        <span></span>
                      </div>
                    </div>
                    <div class="box">
                      <select v-model="lookup_nat">
                        <option v-for="nat in nats" :key="nat">
                          {{ nat }}
                        </option>
                      </select>
                    </div>
                  </div>
                </div>
                <div class="col-sm-8">
                  <div class="card-block">
                    <h6 class="m-b-20 p-b-5 b-b-default f-w-600">
                      Information
                    </h6>
                    <div class="row">
                      <div class="col-sm-6">
                        <p class="m-b-10 f-w-600">Email</p>
                        <h6
                          @dblclick="open('https://temp-mail.org/')"
                          class="text-muted f-w-400"
                        >
                          {{ email }}
                        </h6>
                      </div>
                      <div class="col-sm-6">
                        <p class="m-b-10 f-w-600">Phone</p>
                        <h6
                          @dblclick="open('https://mobilesms.io/')"
                          class="text-muted f-w-400"
                        >
                          {{ phone }}
                        </h6>
                      </div>
                    </div>
                    <h6 class="m-b-20 m-t-40 p-b-5 b-b-default f-w-600">
                      Location
                    </h6>
                    <div class="row">
                      <div class="col-sm-6">
                        <p class="m-b-10 f-w-600">Country</p>
                        <h6
                          @dblclick="copy(address.country)"
                          class="text-muted f-w-400"
                        >
                          {{ address.country }}
                        </h6>
                      </div>
                      <div class="col-sm-6">
                        <p class="m-b-10 f-w-600">Address</p>
                        <h6
                          @dblclick="
                            copy(
                              `${address.street.name} ${address.city} ${address.state} ${address.postcode}`
                            )
                          "
                          class="text-muted f-w-400"
                        >
                          {{ address.city }} {{ address.state }}
                        </h6>
                      </div>
                    </div>
                    <ul class="social-link list-unstyled m-t-40 m-b-10">
                      <li>
                        <a
                          href="https://github.com/kyng-cytro"
                          data-toggle="tooltip"
                          data-placement="bottom"
                          title=""
                          data-original-title="github"
                          data-abc="true"
                          :class="gender"
                          ><i
                            class="mdi mdi-github-circle feather icon-github-circle github-circle"
                            aria-hidden="true"
                          ></i
                        ></a>
                      </li>
                      <li>
                        <a
                          href="https://twitter.com/Cytro"
                          data-toggle="tooltip"
                          data-placement="bottom"
                          title=""
                          data-original-title="twitter"
                          data-abc="true"
                          :class="gender"
                          ><i
                            class="mdi mdi-twitter feather icon-twitter twitter"
                            aria-hidden="true"
                          ></i
                        ></a>
                      </li>
                      <li>
                        <a
                          href="https://www.instagram.com/kyng_cytro/"
                          data-toggle="tooltip"
                          data-placement="bottom"
                          title=""
                          data-original-title="instagram"
                          data-abc="true"
                          :class="gender"
                          ><i
                            class="mdi mdi-instagram feather icon-instagram instagram"
                            aria-hidden="true"
                          ></i
                        ></a>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <button @click="generate" class="button-59">Generate</button>
  </div>
</template>
<script>
import moment from "moment";
export default {
  data() {
    return {
      show_alert: false,
      nats: [
        "Random",
        "AU",
        "BR",
        "CA",
        "CH",
        "DE",
        "DK",
        "ES",
        "FI",
        "FR",
        "GB",
        "IE",
        "IR",
        "NO",
        "NL",
        "NZ",
        "TR",
        "US",
      ],
      lookup_nat: "Random",
      lookup_gender: "random",
      name: "John Doe",
      email: "test@email.com",
      phone: "0123456789",
      gender: "male",
      age: "40",
      dob: "1953-12-06T18:01:01.376Z",
      picture: "https://img.icons8.com/bubbles/100/000000/user.png",
      address: {
        country: "Iran",
        street: {
          number: 5970,
          name: "میدان دکتر فاطمی / جهاد",
        },
        city: "سنندج",
        state: "همدان",
        postcode: 76635,
        coordinates: {
          latitude: "35.6933",
          longitude: "-36.9372",
        },
      },
    };
  },
  async beforeMount() {
    const res = await fetch("https://randomuser.me/api/");
    const { results } = await res.json();
    this.name = results[0].name.first + " " + results[0].name.last;
    this.email = results[0].email;
    this.phone = results[0].cell;
    this.gender = results[0].gender;
    this.age = results[0].dob.age;
    this.dob = results[0].dob.date;
    this.picture = results[0].picture.large;
    this.address = {
      country: results[0].location.country,
      street: {
        number: results[0].location.street.number,
        name: results[0].location.street.name,
      },
      city: results[0].location.city,
      state: results[0].location.state,
      postcode: results[0].location.postcode,
      coordinates: {
        latitude: results[0].location.coordinates.latitude,
        longitude: results[0].location.coordinates.longitude,
      },
    };
  },
  methods: {
    wait(ms) {
      return new Promise((resolve) => setTimeout(resolve, ms));
    },
    async generate() {
      const res = await fetch(
        `https://randomuser.me/api/?nat=${this.lookup_nat}&gender=${this.lookup_gender}`
      );
      const { results } = await res.json();
      this.name = results[0].name.first + " " + results[0].name.last;
      this.email = results[0].email;
      this.phone = results[0].cell;
      this.gender = results[0].gender;
      this.age = results[0].dob.age;
      this.dob = results[0].dob.date;
      this.picture = results[0].picture.large;
      this.address = {
        country: results[0].location.country,
        street: {
          number: results[0].location.street.number,
          name: results[0].location.street.name,
        },
        city: results[0].location.city,
        state: results[0].location.state,
        postcode: results[0].location.postcode,
        coordinates: {
          latitude: results[0].location.coordinates.latitude,
          longitude: results[0].location.coordinates.longitude,
        },
      };
    },
    toggleGender() {},
    async copy(data) {
      this.show_alert = true;
      navigator.clipboard.writeText(data);
      await this.wait(1000);
      this.show_alert = false;
    },
    open(url) {
      window.open(url);
    },
    async copy_date(data) {
      this.show_alert = true;
      navigator.clipboard.writeText(moment(data).format("DD/MM/YYYY"));
      await this.wait(1000);
      this.show_alert = false;
    },
  },
};
</script>
<style scoped>
.container {
  position: relative;
  margin-left: auto;
  margin-right: auto;
  padding: 0px;
}
.alert {
  margin-top: 3rem;
  margin-left: auto;
  margin-right: auto;
  width: 60%;
}

.padding {
  padding: 0 0.5rem 0 0.5rem !important;
}
.user-card-full {
  overflow: hidden;
}

.card {
  border-radius: 5px;
  -webkit-box-shadow: 0 1px 20px 0 rgba(69, 90, 100, 0.08);
  box-shadow: 0 1px 20px 0 rgba(69, 90, 100, 0.08);
  border: none;
  margin-bottom: 30px;
}

.m-r-0 {
  margin-right: 0px;
}

.m-l-0 {
  margin-left: 0px;
}

.user-card-full .user-profile {
  border-radius: 5px 0 0 5px;
}

.bg-c-lite-pink {
  background: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#f29263),
    to(#ee5a6f)
  );
  background: linear-gradient(to right, #ee5a6f, #f29263);
}
.bg-c-lite-blue {
  background: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#6384f2),
    to(#645aee)
  );
  background: linear-gradient(to right, #645aee, #6384f2);
}
.user-profile {
  padding: 20px 0;
}

.card-block {
  padding: 1.25rem;
}

.m-b-25 {
  margin-bottom: 25px;
}

.img-radius {
  border-radius: 50%;
  width: 90px;
}

h6 {
  font-size: 14px;
}

.card .card-block p {
  line-height: 25px;
}

@media only screen and (min-width: 1400px) {
  p {
    font-size: 14px;
  }
}

.card-block {
  padding: 1.25rem;
}

.b-b-default {
  border-bottom: 1px solid #e0e0e0;
}

.m-b-20 {
  margin-bottom: 20px;
}

.p-b-5 {
  padding-bottom: 5px !important;
}

.card .card-block p {
  line-height: 25px;
}

.m-b-10 {
  margin-bottom: 10px;
}

.text-muted {
  color: #919aa3 !important;
}

.b-b-default {
  border-bottom: 1px solid #e0e0e0;
}

.f-w-600 {
  font-weight: 600;
}

.m-b-20 {
  margin-bottom: 20px;
}

.m-t-40 {
  margin-top: 20px;
}

.p-b-5 {
  padding-bottom: 5px !important;
}

.m-b-10 {
  margin-bottom: 10px;
}

.m-t-40 {
  margin-top: 20px;
}

.user-card-full .social-link li {
  display: inline-block;
}

.user-card-full .social-link li a {
  font-size: 20px;
  margin: 0 10px 0 0;
  -webkit-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}

.female {
  color: #f29263;
}
.button-59 {
  margin-bottom: 20px;
  align-items: center;
  background-color: #fff;
  border: 2px solid #000;
  box-sizing: border-box;
  color: #000;
  cursor: pointer;
  display: inline-flex;
  fill: #000;
  font-family: Inter, sans-serif;
  font-size: 16px;
  font-weight: 600;
  height: 48px;
  justify-content: center;
  letter-spacing: -0.8px;
  line-height: 24px;
  min-width: 140px;
  outline: 0;
  padding: 0 17px;
  text-align: center;
  text-decoration: none;
  transition: all 0.3s;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-59:focus {
  color: #171e29;
}

.button-59:hover {
  border-color: #06f;
  color: #06f;
  fill: #06f;
}

.button-59:active {
  border-color: #06f;
  color: #06f;
  fill: #06f;
}

@media (min-width: 768px) {
  .button-59 {
    min-width: 110px;
  }
}
.filters {
  margin-top: 10px;
}
.tw-toggle {
  /* background: #95A5A6; */
  display: inline-block;
  padding: 2px 3px;
  border-radius: 20px;
  position: relative;
  border: 2px solid #95a5a6;
}

.tw-toggle label {
  text-align: center;
  font-family: sans-serif;
  display: inline-block;
  color: #95a5a6;
  position: relative;
  z-index: 2;
  margin: 0;
  text-align: center;
  padding: 2px 6px;
  font-size: 15px;
  /* cursor: pointer; */
}

.tw-toggle input {
  /* display: none; */
  position: absolute;
  z-index: 3;
  opacity: 0;
  cursor: pointer;
}

.tw-toggle span {
  height: 21px;
  width: 21px;
  line-height: 21px;
  border-radius: 50%;
  background: #fff;
  display: block;
  position: absolute;
  left: 22px;
  top: 3.5px;
  transition: all 0.3s ease-in-out;
}

.tw-toggle input[value="female"]:checked ~ span {
  background: #f29263;
  left: 4px;
  color: #fff;
}

.tw-toggle input[value="male"]:checked ~ span {
  background: #6384f2;
  top: 4px;
  left: 55.5px;
}
.tw-toggle input[value="random"]:checked ~ span {
  background: -webkit-gradient(
    linear,
    left top,
    right top,
    from(#6384f2),
    to(#f29263)
  );
  background: linear-gradient(to right, #f29263, #6384f2);
  top: 4.5px;
  left: 28.5px;
}

.tw-toggle input[value="female"]:checked + label,
.tw-toggle input[value="male"]:checked + label {
  color: #fff;
}
.tw-toggle input[value="random"]:checked + label {
  color: #fff;
}
.box {
  margin-top: 15px;
  margin-bottom: 15px;
}
.box select {
  background-color: #fff;
  text-align: center;
  font-family: Inter, sans-serif;
  font-size: 16px;
  font-weight: 600;
  letter-spacing: -0.8px;
  line-height: 24px;
  transition: all 0.3s;
  padding: 5px 1px;
  border: 2px solid #000;
}
.box select:focus {
  outline: none;
}
</style>
