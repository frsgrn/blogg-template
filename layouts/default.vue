<template>
  <div>
    <div class="e-p-content">
      <navbar></navbar>
      <nuxt />
    </div>
    <e-p-footer></e-p-footer>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar";
import Footer from "@/components/Footer";

export default {
  components: {
    Navbar,
    EPFooter: Footer,
  },
  mounted() {    
    var userLang = navigator.language || navigator.userLanguage;
    console.log("detected language: " + userLang)
    if (userLang == "sv-SE" || userLang == "sv") this.$store.commit('SET_LANGUAGE', {lang: "swedish"})
  }
};
</script>

<style>
.e-p-content {
  /* change calc() when footer height changes */
  min-height: calc(100vh - 228px);
}

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: normal;
}

p {
  font-size: 17px;
  margin-bottom: 8px;
}

body {
  font-family: 'Jost', sans-serif;
  background-color: #f3f5f7;
  word-wrap: break-word;
  height: 100%;
  padding-top: 100px;
}

a {
  color: inherit;
  text-decoration: inherit;
}

a:hover {
  color: inherit;
  text-decoration: inherit;
}

p a:hover {
  text-decoration: underline;
  color: #0832a5;
}

p a {
  color: #0d4eff;
}

.section {
  margin-bottom: 30px;
}

.bold-link {
  border-bottom: 2px solid black;
  display: inline;
  font-weight: bold;
}

.article {
  background-color: white;
}

.fancy-article-list {
  background-color: transparent;
  box-shadow: none !important;
}

.article-preview {
  margin: 0px 0px 10px 0px;
  padding: 20px;
  background-color: white;
  box-shadow: 0 3px 8px 0 rgba(0, 0, 0, 0.03);
  border-radius: 5px;

  overflow: hidden;
}

.article-preview .body-preview {
  max-height: 100px;
  font-size: 17px;
  overflow: hidden;
}

.article-preview p {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.article-preview * {
  margin: 0px;
}

.paper {
  border-radius: 5px;
  margin-bottom: 20px;
  padding-top: 35px;
  text-align: center;
  box-shadow: 0 3px 8px 0 rgba(0, 0, 0, 0.03);
  margin: auto;
  padding: 25px;
}

.paper .content {
  max-width: 700px;
  margin: auto;
  text-align: left;
}

.article p {
  color: #35384e;
}

.subject-preview {
  margin: 0px 0px 10px 0px;
  padding: 20px;
  background-color: white;
  box-shadow: 0 3px 8px 0 rgba(0, 0, 0, 0.03);
  border-radius: 5px;
}

.subject-preview p {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.subject-preview * {
  margin: 0px;
}

.body img {
  width: 100%;
}

.muted-dark {
  color: #303030;
}

.muted-light {
  color: #00000090;
}

.semi-bold, b {
  font-weight: 600;
}

.bold {
  font-weight: 700;
}
</style>
