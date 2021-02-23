<template>
  <Main />
  <About />
  <Footer />
</template>

<script>
import Main from "./components/Main";
import About from "./components/About"
import Footer from "./components/Footer"

export default {
  name: "App",
  components: {
    Main, About, Footer
  }
};
</script>

<style scoped></style>
