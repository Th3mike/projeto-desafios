<template>
  <main>
    <Navbar />
    <Nuxt />
    <Footer />
  </main>
</template>

<script>
/* Páginas */
import Navbar from "../components/navbar";
import Footer from "../components/footer";

export default {
  components: {
    Navbar,
    Footer,
  },
};
</script>

<style>
@media only screen and (max-width: 600px) {
  main {
    width: 100%;
    height: 900px;
    margin: 0 auto;
  }
}
</style>
