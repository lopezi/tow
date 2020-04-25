<template>
  <div class="home">
    <mu-container class="demo-container">
      <mu-row gutter>
        <mu-appbar style="width: 100%;" color="white">
          <img width="77" slot="left" src="../assets/tow-logo.svg" />
        </mu-appbar>
      </mu-row>
      <mu-paper style="margin:20px -8px 0 -8px;" :z-depth="5">
        <mu-row >
          <mu-col span="12" sm="12" md="6">
              <div class="grid-cell">
                <mu-flex class="flex-demo" justify-content="center" fill>
                  <iframe class="video-player video-player--banner" src="iframes/tree/index.html"></iframe>
                </mu-flex>
              </div>
          </mu-col>
          <mu-col span="12" sm="12" md="6">
            <div class="grid-cell">
                <mu-flex class="flex-demo" justify-content="center" fill>
                  <mu-container class="email">
                    <h1>Take your data back from big tech and get paid</h1>
                    <mu-form ref="form" :model="validateForm" class="mu-demo-form">
                      <mu-form-item label="Email" help-text="Be the first to control your data em win ToW tokens" prop="email" :rules="emailRules">
                        <mu-text-field v-model="validateForm.email" prop="Email"></mu-text-field>
                      </mu-form-item>
                      <mu-form-item>
                        <mu-button style="margin-left:0;" color="primary" @click="submit">submit</mu-button>
                      </mu-form-item>
                    </mu-form>
                  </mu-container>
                </mu-flex>
            </div>
          </mu-col>
        </mu-row>
      </mu-paper>

      <mu-row>
        <mu-col span="12" sm="12" md="6">
          <div class="grid-cell">
            <mu-flex class="flex-demo" justify-content="center" fill>
              <mu-container class="email">
                <h1>Get paid for data on Tree of Wally</h1>
                <p>You share data with internet platforms without getting its value in return. Tree of Wally - or ToW - makes getting the value in your data easy. </p>
              </mu-container>
            </mu-flex>
          </div>
        </mu-col>
        <mu-col span="12" sm="12" md="6">
          <div class="grid-cell">
            <mu-flex style="padding: 5vw;height:444px;background-color: dodgerblue;" class="flex-demo" justify-content="center" fill>
              <!--<img style="width: 100%;" alt="ToW rings" src="../assets/rings.svg" />-->
            </mu-flex>
          </div>
        </mu-col>
      </mu-row>
      <mu-row>
        <mu-col span="12" sm="12" md="6">
          <div class="grid-cell">
            <mu-flex style="padding: 5vw;height:444px;background-color: dodgerblue;" class="flex-demo" justify-content="center" fill>

            </mu-flex>
          </div>
        </mu-col>
        <mu-col span="12" sm="12" md="6">
          <div class="grid-cell">
            <mu-flex class="flex-demo" justify-content="center" fill>
              <mu-container class="email">
                <h1>How ToW works</h1>
                <p>ToW gives you “data credits” — Wallys — everyday for access to your data. ToW enforces your data rights against violators using CCPA and GDPR privacy laws. Wallys are a medium of exchange to track content views in ToW’s ecosystem, beginning with a native social network. Wallys are good currency, widely distributed with stable market-priced exchange-rates.
                </p>
              </mu-container>
            </mu-flex>
          </div>
        </mu-col>
      </mu-row>
      <mu-row>
        <mu-col span="12" sm="12" md="6">
          <div class="grid-cell">
            <mu-flex class="flex-demo" justify-content="center" fill>
              <mu-container class="email">
                <h1>Financial leverage in your pocket.</h1>
                <p>Payments to buy ads in the ToW ecosystem are settled in Wallys. Therefore, as businesses allocate budget for ads on ToW, they pay dollars to buy Wallys from consumers on the app. </p>
              </mu-container>
            </mu-flex>
          </div>
        </mu-col>
        <mu-col span="12" sm="12" md="6">
          <div class="grid-cell">
            <mu-flex style="height:444px;background-color: dodgerblue;" class="flex-demo" justify-content="center" fill>
              <mu-container class="email">

              </mu-container>
            </mu-flex>
          </div>
        </mu-col>
      </mu-row>
      <Footer></Footer>

    </mu-container>

  </div>
</template>

<script>
// @ is an alias to /src

import Footer       from '../components/Footer';

export default {
  name: 'Home',
  components: {
    'Footer': Footer,
  },
  data () {
    return {
      emailRules: [
        { validate: (val) => !!val, message: 'Email must be filled in'},
        { validate: (val) => val.length >= 3, message: 'Username length greater than 3'}
      ],
      validateForm: {
        email: ''
      }
    }
  },
  methods: {
    submit () {
      this.$refs.form.validate().then((result) => {
        console.log('form valid: ', result)
      });
    },
    scrollToTop() {
      window.scrollTo(0,0);
    }
  }
};
</script>

<style scoped lang="scss">
  .flex-wrapper {
    width: 100%;
  }
  .video-player {
    border: none;
    width: 100%;
    height: 100%;
  }
  .video-player--banner {
    position: relative;
    height: 444px;
  }
  @media only screen and (min-width: 768px) {
    .email {
      margin-top: 60px;
    }
  }
  .email {
    padding: 0 4vw 0 4vw;
    .mu-form-item-label {
      text-align: left;
    }
  }
</style>


