<template>
  <div>
    <div
      class="hero"
      style="border-bottom: 2px solid #eee; padding-bottom: 10px; margin-bottom: 20px;"
    >
      <div>
        <div style="text-align: center; margin-bottom: 30px;">
          <h1 style="font-weight: bold; font-size: 50px;">{{this.$store.state.siteInfo.sitename}}</h1>
          <p class="muted-dark">{{this.$store.state.siteInfo.sitedescription}}</p>
        </div>
        <div style="display: inline; cursor: pointer;" v-on:click="toggleMoreInformation()">
          <div class="profile" style="float: left;"></div>
          <div class="information">
            <h4 style="margin: 0px;">Ossi Pesämaa</h4>
            <p>
              <span class="toggleIcon">
                <span v-if="!toggled"><i class="fas fa-caret-down"></i></span>
                <span v-else><i class="fas fa-caret-up"></i></span>
              </span>
              Associate professor at Luleå University of Technology in Sweden
            </p>
          </div>
        </div>
        <div :hidden="!toggled">
          <p class="contact-information">
            <span>
              <i class="fas fa-mobile-alt"></i> +49703248747
            </span>
            <span>
              <i class="far fa-envelope"></i> email@example.com
            </span>
          </p>
          <div
            class="more-information"
            v-if="this.$store.state.siteInfo.about"
            v-html="$md.render(this.$store.state.siteInfo.about)"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["title", "subheadline"],
  data() {
    return {
      toggled: false
    };
  },
  methods: {
    toggleMoreInformation() {
      this.toggled = !this.toggled;
    }
  }
};
</script>
<style>
.hero .header-hero {
  color: white;
  padding: 30px;
  margin-bottom: 40px;
  border-radius: 15px;
  background-color: #241d2f;
  border-bottom: 5px solid black;
  text-align: center;
}

.contact-information span {
  margin-right: 20px;
  white-space: nowrap;
}

.hero .profile {
  position: relative;
}

.hero .profile {
  width: 53px;
  height: 53px;
  background-image: url("/profile.jpeg");
  background-size: cover;
  background-repeat: no-repeat;
  border-radius: 100%;
  margin-right: 20px;
}

@media screen and (max-width: 800px) {
  .hero .profile {
    float: none !important;
    margin-bottom: 15px;
    text-align: center;
    margin: auto;
  }
  .hero .information {
    text-align: center;
  }
}
</style>
