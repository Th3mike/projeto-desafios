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
main {
  height: 600px;
}
</style>
