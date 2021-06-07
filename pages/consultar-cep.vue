<template>
  <div class="container d-flex justify-content-center">
    <div>
      <h3 class="display-3 text-dark">Consulte seu CEP</h3>
      <form method="get" action=".">
        <p id="erro" class="text-danger text-center">
          <strong>
            {{ erro }}
          </strong>
        </p>
        <p id="sucesso" class="text-success text-center">
          <strong>
            {{ sucesso }}
          </strong>
        </p>
        <input
          class="form-control form-control-lg mt-2"
          type="text"
          placeholder="Insira o CEP"
          v-model="cep"
          maxlength="8"
          @keypress="onlynumber($event)"
          @blur="pesquisacep()"
        />
        <fieldset disabled>
          <label for="rua" class="mt-2">Rua:</label>
          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="Rua"
            v-model="logradouro"
          />
          <label for="complemento" class="mt-2">Complemento:</label>
          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="Complemento"
            v-model="complemento"
          />
          <label for="bairro" class="mt-2">Bairro:</label>
          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="Bairro"
            v-model="bairro"
          />
          <label for="cidade" class="mt-2">Cidade:</label>
          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="Cidade"
            v-model="localidade"
          />
          <label for="estado" class="mt-2">Estado:</label>
          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="Estado"
            v-model="uf"
          />
          <!---
          <label for="ibge" class="mt-2">IBGE:</label>
          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="IBGE"
            v-model="ibge"
          />

          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="gia"
            v-model="gia"
          />
          --->
          <label for="ddd" class="mt-2">DDD:</label>
          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="DDD"
            v-model="ddd"
          />
          <!---
          <input
            class="form-control form-control-lg"
            type="text"
            placeholder="siafi"
            v-model="siafi"
          />
          --->
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
      ddd: null,
      /* ibge: null,
      gia: null,
      siafi: null,
      */
    };
  },
  methods: {
    onlynumber(evt) {
      var theEvent = evt || window.event;
      var key = theEvent.keyCode || theEvent.which;
      key = String.fromCharCode(key);
      //Aceitar somente teclas 0 à 9
      var regex = /^[0-9.]+$/;
      if (!regex.test(key)) {
        theEvent.returnValue = false;
        if (theEvent.preventDefault) theEvent.preventDefault();
      }
    },
    pesquisacep() {
      //Expressão regular para validar o CEP.
      var validacep = /^[0-9]{8}$/;
      if (validacep.test(this.cep)) {
        axios
          .get(`https://viacep.com.br/ws/${this.cep}/json/`)
          .then((result) => {
            this.sucesso = "✔️ Encontramos o CEP que você inseriu!";
            this.erro = null;
            this.logradouro = result.data.logradouro;
            this.complemento = result.data.complemento;
            this.bairro = result.data.bairro;
            this.localidade = result.data.localidade;
            this.uf = result.data.uf;
            this.ddd = result.data.ddd;
            setTimeout(() => {
              this.sucesso;
            }, 10000);
            /*this.ibge = result.data.ibge;
            this.gia = result.data.gia;
            this.siafi = result.data.siafi;
            */
          });
      } else {
        setTimeout(() => {
          this.erro;
        }, 10000);
        this.logradouro =
          this.complemento =
          this.bairro =
          this.localidade =
          this.uf =
          this.ddd =
            "";
        this.erro = "❌ CEP inválido";
        this.sucesso = null;
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
  label {
    font-size: 15px;
  }
  input {
    height: 20px;
  }
  img {
    display: none;
  }
  h3 {
    font-size: 30px;
  }
}
@media only screen and (max-width: 600px) {
  h3 {
    font-size: 25px;
  }
}
</style>
