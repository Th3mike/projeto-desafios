<template>
  <header class="sticky-top background-nav-footer d-flex justify-content-center h4">
      <b-navbar toggleable="lg" type="dark">
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <b-navbar-nav>
            <b-nav-item class="ml-5" href="/">Início</b-nav-item>
            <b-nav-item class="ml-5" href="/instagram">Instagram</b-nav-item>
            <b-nav-item class="ml-5" href="/form-login">Formulário de Login</b-nav-item>
            <b-nav-item class="ml-5" href="/form-endereco">Formuário de Endereço</b-nav-item>
            <b-nav-item class="ml-5" href="/form-endereco-api">API</b-nav-item>
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
