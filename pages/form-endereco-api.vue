<template>
  <div class="container d-flex justify-content-center mt-5 mb-5">
    <div>
    <h1 class="text-center display-6 text-dark">USD para BRL</h1>
    <br>
    <form class="form-inline">
      <div class="form-group mx-sm-3 mb-2" id="app">
        <input
          type="text"
          class="form-control"
          placeholder="Valor"
          v-model="valor"
          onkeypress="return event.charCode >= 48 && event.charCode <= 57"
        />
      </div>
      <button type="submit" class="btn btn-dark mb-2">Calcular</button>
    </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      valor: null,
      resultado: null,
      data: null,
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
  },
};
</script>
