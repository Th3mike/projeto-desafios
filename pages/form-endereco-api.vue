<template>
  <div id="app">
    <h1 class="text-center">Conversor de Moedas</h1>

    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL"></Conversor>
      <Conversor moeda-a="BRL" moeda-b="USD"></Conversor>
    </div>

    <div class="linha">
      <Conversor moeda-a="CAD" moeda-b="BRL"></Conversor>
      <Conversor moeda-a="BRL" moeda-b="CAD"></Conversor>
    </div>

    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL"></Conversor>
      <Conversor moeda-a="BRL" moeda-b="EUR"></Conversor>
    </div>
  </div>
</template>

<script>
import Conversor from "../components/Conversor.vue";
export default {
  name: "app",
  components: {
    Conversor,
  },
};
</script>

