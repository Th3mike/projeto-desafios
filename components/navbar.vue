<template>
  <header class="sticky-top background-nav-footer d-flex h4">
      <b-navbar toggleable="lg" type="dark">
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item class="ml-5" href="/">Início</b-nav-item>
            <b-nav-item class="ml-5" href="/instagram">Instagram</b-nav-item>
            <b-nav-item class="ml-5" href="/form-login">Inscrição</b-nav-item>
            <b-nav-item class="ml-5" href="/form-endereco">Consultar Cep</b-nav-item>
            <b-nav-item class="ml-5" href="/form-endereco-api">Converter moeda</b-nav-item>
          </b-navbar-nav>
        </b-collapse>
      </b-navbar>
  </header>
</template>

<style>
.background-nav-footer {
  background-color: black;
}
</style>
