<template>
  <div class="container d-flex justify-content-center meio background">
    <div>
      <label><strong>De</strong></label>
      <select class="custom-select" id="primeira_moeda">
        <option value="AED">AED</option>
        <option value="ARS">ARS</option>
        <option value="AUD">AUD</option>
        <option value="BGN">BGN</option>
        <option value="BRL">BRL</option>
        <option value="BSD">BSD</option>
        <option value="CAD">CAD</option>
        <option value="CHF">CHF</option>
        <option value="CLP">CLP</option>
        <option value="CNY">CNY</option>
        <option value="COP">COP</option>
        <option value="CZK">CZK</option>
        <option value="DKK">DKK</option>
        <option value="DOP">DOP</option>
        <option value="EGP">EGP</option>
        <option value="EUR">EUR</option>
        <option value="FJD">FJD</option>
        <option value="GBP">GBP</option>
        <option value="GTQ">GTQ</option>
        <option value="HKD">HKD</option>
        <option value="HRK">HRK</option>
        <option value="HUF">HUF</option>
        <option value="IDR">IDR</option>
        <option value="ILS">ILS</option>
        <option value="INR">INR</option>
        <option value="ISK">ISK</option>
        <option value="JPY">JPY</option>
        <option value="KRW">KRW</option>
        <option value="KZT">KZT</option>
        <option value="MXN">MXN</option>
        <option value="MYR">MYR</option>
        <option value="NOK">NOK</option>
        <option value="NZD">NZD</option>
        <option value="PAB">PAB</option>
        <option value="PEN">PEN</option>
        <option value="PHP">PHP</option>
        <option value="PKR">PKR</option>
        <option value="PLN">PLN</option>
        <option value="PYG">PYG</option>
        <option value="RON">RON</option>
        <option value="RUB">RUB</option>
        <option value="SAR">SAR</option>
        <option value="SEK">SEK</option>
        <option value="SGD">SGD</option>
        <option value="THB">THB</option>
        <option value="TRY">TRY</option>
        <option value="TWD">TWD</option>
        <option value="UAH">UAH</option>
        <option value="USD" selected>USD</option>
        <option value="UYU">UYU</option>
        <option value="VND">VND</option>
        <option value="ZAR">ZAR</option>
      </select>
      <input
        type="number"
        class="form-control form-control-lg mt-2"
        id="valor_primeira_moeda"
        value="1"
        @keypress="onlynumber($event),converter()"
      />
    </div>
    <div class="ml-5 mt-5 mobile" id="rate"></div>
    <div class="ml-5">
      <label><strong>Para</strong></label>
      <select class="custom-select" id="segunda_moeda">
        <option value="AED">AED</option>
        <option value="ARS">ARS</option>
        <option value="AUD">AUD</option>
        <option value="BGN">BGN</option>
        <option value="BRL" selected>BRL</option>
        <option value="BSD">BSD</option>
        <option value="CAD">CAD</option>
        <option value="CHF">CHF</option>
        <option value="CLP">CLP</option>
        <option value="CNY">CNY</option>
        <option value="COP">COP</option>
        <option value="CZK">CZK</option>
        <option value="DKK">DKK</option>
        <option value="DOP">DOP</option>
        <option value="EGP">EGP</option>
        <option value="EUR">EUR</option>
        <option value="FJD">FJD</option>
        <option value="GBP">GBP</option>
        <option value="GTQ">GTQ</option>
        <option value="HKD">HKD</option>
        <option value="HRK">HRK</option>
        <option value="HUF">HUF</option>
        <option value="IDR">IDR</option>
        <option value="ILS">ILS</option>
        <option value="INR">INR</option>
        <option value="ISK">ISK</option>
        <option value="JPY">JPY</option>
        <option value="KRW">KRW</option>
        <option value="KZT">KZT</option>
        <option value="MXN">MXN</option>
        <option value="MYR">MYR</option>
        <option value="NOK">NOK</option>
        <option value="NZD">NZD</option>
        <option value="PAB">PAB</option>
        <option value="PEN">PEN</option>
        <option value="PHP">PHP</option>
        <option value="PKR">PKR</option>
        <option value="PLN">PLN</option>
        <option value="PYG">PYG</option>
        <option value="RON">RON</option>
        <option value="RUB">RUB</option>
        <option value="SAR">SAR</option>
        <option value="SEK">SEK</option>
        <option value="SGD">SGD</option>
        <option value="THB">THB</option>
        <option value="TRY">TRY</option>
        <option value="TWD">TWD</option>
        <option value="UAH">UAH</option>
        <option value="USD">USD</option>
        <option value="UYU">UYU</option>
        <option value="VND">VND</option>
        <option value="ZAR">ZAR</option>
      </select>
      <input
        type="number"
        class="form-control form-control-lg mt-2"
        id="valor_segunda_moeda"
        placeholder="0"
        disabled
      />
    </div>
    <img src="../assets/onda.svg" alt="SVG ONDA"/>
  </div>
</template>

<script>
export default {
  name: "app",
  methods: {
    //Para colocar somente números no input
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
      //criar var para o primeiro select, pegando o valor do selecionado
      const primeira_moeda1 = primeira_moeda.value;
      //criar var para o segundo select, pegando o valor do selecionado
      const segunda_moeda1 = segunda_moeda.value;
      //Utilizei Fetch para acessar e manipular o json, com axios não obtive o resultado que eu tive com o fetch.
      //Conecta até a API com o primeiro select
      fetch(`https://api.exchangerate-api.com/v4/latest/${primeira_moeda1}`)
        //Resgata as informações do json
        .then((res) => res.json())
        //mostra o resultado do primeiro select (a conversão)
        .then((res) => {
          const new_rate = res.rates[segunda_moeda1];
          //mostra a conversão nos dois inputs
          rate.innerText = `1 ${primeira_moeda1} = ${new_rate} ${segunda_moeda1}`;
          //Mostra o valor da segunda moeda sendo convertida pela primeira
          valor_segunda_moeda.value =
            //Mostra o valor do primeiro select (seria a div com o id="rate", mostrando a conversão sempre em 1)
            (valor_primeira_moeda.value * new_rate).toFixed(2);
        });
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
.meio {
  margin-top: 18%;
}
.background {
  width: 40%;
  height: 140px;
  background: whitesmoke;
  box-shadow: 0px 10px 15px 5px rgba(12, 12, 12, 0.25);
}
@media only screen and (max-width: 1280px) {
    img {
    display: none;
  }
}
@media only screen and (max-width: 600px) {
  .background {
    width: 100%;
    height: 180px;
    border-radius: 30px;
  }
  input {
    width: 100%;
  }
  .meio {
  margin-top: 50%;
}
  .mobile {
    display: none;
  }
}
</style>
