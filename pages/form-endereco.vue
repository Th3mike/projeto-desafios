<template>
  <div class="container d-flex justify-content-center app">
    <div>
      <h3 class="display-3 text-dark">Consulte seu CEP</h3>
      <form method="get" action=".">
        <input
          class="form-control form-control-lg mt-2"
          type="text"
          placeholder="CEP"
          v-model="cep"
          @blur="pesquisacep()"
        />
        <fieldset disabled>
          <input
            class="form-control form-control-lg mt-2"
            type="text"
            placeholder="logradouro"
            v-model="logradouro"
          />
          <input
            class="form-control form-control-lg mt-2"
            type="text"
            placeholder="complemento"
            v-model="complemento"
          />
          <input
            class="form-control form-control-lg mt-2"
            type="text"
            placeholder="bairro"
            v-model="bairro"
          />
          <input
            class="form-control form-control-lg mt-2"
            type="text"
            placeholder="localidade"
            v-model="localidade"
          />
          <input
            class="form-control form-control-lg mt-2"
            type="text"
            placeholder="uf"
            v-model="uf"
          />
          <input
            class="form-control form-control-lg mt-2"
            type="text"
            placeholder="ibge"
            v-model="ibge"
          />
          <input
            class="form-control form-control-lg mt-2"
            type="text"
            placeholder="gia"
            v-model="gia"
          />
          <input
            class="form-control form-control-lg mt-2"
            type="text"
            placeholder="ddd"
            v-model="ddd"
          />
          <input
            class="form-control form-control-lg mt-2 mb-2"
            type="text"
            placeholder="siafi"
            v-model="siafi"
          />
        </fieldset>
      </form>
    </div>
    <img src="../assets/onda.svg" alt="SVG ONDA" />
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      cep: null,
      data: null,
      logradouro: null,
      complemento: null,
      bairro: null,
      localidade: null,
      uf: null,
      ibge: null,
      gia: null,
      ddd: null,
      siafi: null,
    };
  },
  methods: {
    pesquisacep() {
      if (this.cep) {
        axios
          .get(`https://viacep.com.br/ws/${this.cep}/json/`)
          .then((result) => {
            this.logradouro = result.data.logradouro;
            this.complemento = result.data.complemento;
            this.bairro = result.data.bairro;
            this.localidade = result.data.localidade;
            this.uf = result.data.uf;
            this.ibge = result.data.ibge;
            this.gia = result.data.gia;
            this.ddd = result.data.ddd;
            this.siafi = result.data.siafi;
          });
      }
    },
  },
};
</script>

<style scoped>
img {
  position: absolute;
  width: 100%;
  bottom: 0;
}
@media only screen and (max-width: 1280px) {
  input {
    height: 30px;
  }
  img {
    display: none;
}
  h3 {
    font-size: 40px;
  }
}
</style>
