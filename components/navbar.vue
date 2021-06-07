<template>
  <header class="sticky-top background-nav-footer d-flex h4 mobile-nav">
    <b-navbar toggleable="lg" type="dark">
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item class="ml-5"
            ><NuxtLink to="/">Início</NuxtLink></b-nav-item
          >
          <b-nav-item class="ml-5"
            ><NuxtLink to="/instagram">Instagram</NuxtLink></b-nav-item
          >
          <b-nav-item class="ml-5"
            ><NuxtLink to="/inscricao">Inscrição</NuxtLink></b-nav-item
          >
          <b-nav-item class="ml-5"
            ><NuxtLink to="/consultar-cep">Consultar Cep</NuxtLink></b-nav-item
          >
          <b-nav-item class="ml-5"
            ><NuxtLink to="/converter-moeda"
              >Converter Moeda</NuxtLink
            ></b-nav-item
          >
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </header>
</template>

<style>
.mobile-nav {
  justify-content: center;
}
.background-nav-footer {
  background-color: black;
}
@media only screen and (max-width: 600px) {
  .mobile-nav {
    justify-content: start;
  }
}
</style>
<style scoped>
a {
  color: rgba(255, 255, 255, 0.699);
  text-decoration: none;
}
a:hover {
  color: rgba(255, 255, 255, 0.89);
  text-decoration: none;
}
a.nuxt-link-active {
  font-weight: bold;
}
a.nuxt-link-exact-active {
  color: white;
}
</style>
