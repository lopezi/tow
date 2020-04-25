<template>
  <div class="home">
    <mu-container class="demo-container">
      <mu-row gutter>
        <mu-appbar style="width: 100%;" color="white">
          <img width="82" slot="left" src="../assets/tow-logo.svg" />
        </mu-appbar>
      </mu-row>
      <mu-paper style="margin-left: -8px; margin-right:-8px;" :z-depth="5">
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

    </mu-container>

  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  components: {

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
      margin-top: 80px;
    }
  }
  .email {
    .mu-form-item-label {
      text-align: left;
    }
  }
</style>


