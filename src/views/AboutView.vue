<template>
  <div class="container">
    <div class="padding">
      <div class="row container d-flex justify-content-center">
        <div class="col-xl-8 col-md-12">
          <div class="card user-card-full">
            <div class="row m-l-0 m-r-0">
              <div class="col-sm-4 bg-c-lite-pink user-profile">
                <div class="card-block text-center text-white">
                  <div class="m-b-25">
                    <img
                      src="https://i.ibb.co/c89CKZQ/photo-2022-05-04-09-01-44.jpg"
                      class="img-radius"
                      alt="User-Profile-Image"
                    />
                  </div>
                  <h6 class="f-w-600">Kyng Cytro</h6>
                  <p>Developer</p>
                </div>
              </div>
              <div class="col-sm-8">
                <div class="card-block">
                  <h6 class="m-b-20 p-b-5 b-b-default f-w-600">Version</h6>
                  <div class="row">
                    <div class="col-sm-6">
                      <p class="m-b-10 f-w-600">Gen</p>
                      <h6
                        @dblclick="open('https://github.com/kyng-cytro')"
                        class="text-muted f-w-400"
                      >
                        @1.0.1
                      </h6>
                    </div>
                    <div class="col-sm-6">
                      <p class="m-b-10 f-w-600">Api</p>
                      <h6
                        @dblclick="open('https://randomuser.me/')"
                        class="text-muted f-w-400"
                      >
                        @1.3.0
                      </h6>
                    </div>
                  </div>
                  <h6 class="m-b-20 m-t-40 p-b-5 b-b-default f-w-600">
                    Details
                  </h6>
                  <div class="row">
                    <div class="col-sm-6">
                      <p class="m-b-10 f-w-600">Techologies</p>
                      <h6 class="text-muted f-w-400">Vue3, Bootstrap5</h6>
                    </div>
                    <div class="col-sm-6">
                      <p class="m-b-10 f-w-600">Usage</p>
                      <h6 class="text-muted f-w-400">
                        Double tap any value to copy
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
</template>
<style scoped>
.container {
  position: relative;
  margin-left: auto;
  margin-right: auto;
  padding: 0px;
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
</style>
