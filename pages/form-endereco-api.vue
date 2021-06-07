<template>
  <div class="container d-flex justify-content-center mt-5 mb-5" id="app">
    <div>
      <h1 class="text-center display-6 text-dark">USD para BRL</h1>
      <br />
      <form class="form-inline" method="get" action=".">
        <div class="form-group mx-sm-3 mb-2">
          <input
            type="text"
            class="form-control"
            placeholder="Valor"
            v-model="valor"
            @blur="converter()"
            onkeypress="return event.charCode >= 48 && event.charCode <= 57"
          />
            <input
              type="text"
              class="form-control"
              placeholder="Resultado"
              v-model="resultado"
              disabled
            />
          <button class="btn btn-dark ml-2" @onclick="converter()">Converter</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "app",
  data() {
    return {
      valor: null,
      data: null,
      resultado: null,
    };
  },
  methods: {
    onlynumber(evt) {
      var theEvent = evt || window.event;
      var key = theEvent.keyCode || theEvent.which;
      key = String.fromCharCode(key);
      var regex = /^[0-9.]+$/;
      if (!regex.test(key)) {
        theEvent.returnValue = false;
        if (theEvent.preventDefault) theEvent.preventDefault();
      }
    },
    converter() {
      //Expressão regular para validar o CEP.
      var validacampo = /^[0-9]$/;
      if (validacampo.test(this.valor)) {
        axios
          .get(
            `https://free.currconv.com/api/v7/convert?q=BRL_USD,USD_BRL&compact=ultra&apiKey=a7bb3a7df16277a000c1`
          )
          .then((result) => {
            this.resultado = result.data.resultado;
          });
      } else {
        alert("erro");
      }
    },
  },
};
</script>

<style scoped>
@media only screen and (max-width: 600px) {
  form {
    justify-content: center;
    margin-top: 10px;
  }
  input, button {
    margin-top: 10px;
  }
  button {
    float: right;
  }
}
</style>
