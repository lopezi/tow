<template>
  <mu-container style="background: #EEEEEE;" fluid>
    <mu-row>
      <mu-col span="12" sm="12" md="3">
        <div class="grid-cell">
          <mu-flex class="flex-wrapper" align-items="center">
            <mu-flex style="padding:20px;"  justify-content="center" direction="column" fill>
              <img width="82" src="../assets/tow-logo.svg" />
              <h3 style="padding-top: 5px;">Tree of Wally</h3>
              <p class="wemakeittext" style="margin-top:0;">This is ToW</p>
            </mu-flex>
          </mu-flex>
        </div>
      </mu-col>
      <mu-col span="12" sm="12" md="3">
        <div class="grid-cell footer">
          <mu-flex class="flex-wrapper" align-items="center">
            <mu-flex style="padding:76px 20px 20px;" justify-content="center" align-items="center" direction="column" fill>
              <router-link @click.native="$scrollToTop" to="/">one</router-link>
            </mu-flex>
          </mu-flex>
        </div>
      </mu-col>
      <mu-col span="12" sm="12" md="3">
        <div class="grid-cell footer">
          <mu-flex class="flex-wrapper" align-items="center">
            <mu-flex style="padding:76px 20px 20px;" justify-content="center" align-items="center" direction="column" fill>
              <router-link @click.native="$scrollToTop" to="/services">footer</router-link>
            </mu-flex>
          </mu-flex>
        </div>
      </mu-col>
      <mu-col span="12" sm="12" md="3">
        <div class="grid-cell footer">
          <mu-flex class="flex-wrapper" align-items="center">
            <mu-flex style="padding-top:76px;" justify-content="center" align-items="center" direction="column" fill>
              <router-link to="/contact">here</router-link>
            </mu-flex>
          </mu-flex>
        </div>
      </mu-col>
    </mu-row>
  </mu-container>

</template>

<script>
  export default {
    name: "Footer",
    methods: {
      scrollToTop() {
        window.scrollTo(0,0);
      }
    }
  }
</script>

<style lang="scss">
  @media only screen and (max-width: 767px) {
    .footer {
      a {
        font-size: 4vw;
        line-height: 12vw;
      }
    }
    .wemakeittext {
      font-size: 18px;
    }
  }
  .footer {
    a {
      color: dodgerblue;
    }
  }
</style>
