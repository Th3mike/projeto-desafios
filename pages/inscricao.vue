<template>
  <div
    class="container d-flex justify-content-center flex-column mobile"
    id="app"
  >
    <div class="text-center">
      <h3 class="display-3">
        Seja uma compiladora❤️
        <br />
        <small class="text-muted">Faça sua inscrição abaixo</small>
      </h3>
    </div>
    <div class="container d-flex justify-content-center">
      <form
        v-on:submit.prevent="checkForm"
        class="background zoomIn"
        method="post"
        novalidate
      >
              <p v-if="successfull.length">
    <b v-for="success in successfull" :key="success">{{ success }}</b>
  </p>
        <p v-if="errors.length">
    <b>Por favor, corrija o(s) seguinte(s) erro(s):</b>
    <ul>
      <li v-for="error in errors" :key="error">❌{{ error }}</li>
    </ul>
  </p>
        <div class="form-group">
          <label for="name"
            ><strong>Nome<span style="color: red">*</span></strong></label
          >
          <input
            type="text"
            class="form-control"
            id="name"
            name="name"
            v-model="name"
            @keypress="isLetter($event)"
            placeholder="Bianca Pereira"
          />
        </div>
        <div class="form-group">
          <label for="email" class="mt-2"
            ><strong>E-mail<span style="color: red">*</span></strong></label
          >
          <input
            type="email" v-model="email"
            class="form-control"
            id="email"
            placeholder="bianca-pereira@hotmail.com"
          />
        </div>
        <button type="submit" value="enviar" class="btn btn-dark mt-2">
          Enviar
        </button>
      </form>
      <img src="../assets/onda.svg" alt="SVG ONDA"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      errors: [],
      successfull: [],
      name: null,
      email: null,
    };
  },
  methods: {
    validEmail: function (email) {
      var re =
        /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(email);
    },
    isLetter(e) {
      let char = String.fromCharCode(e.keyCode);
      if (/^[A-Za-z- ]+$/.test(char)) return true;
      else e.preventDefault();
    },
    checkForm: function () {
      this.errors = [];
      this.successfull = [];

      if (!this.name) {
        this.errors.push("O nome é obrigatório.");
      } else if (!this.email) {
        this.errors.push("O e-mail é obrigatório.");
      } else if (!this.validEmail(this.email)) {
        this.errors.push("Utilize um e-mail válido.");
      } else if (this.name && this.email) {
        this.successfull.push("✔️ Sua inscrição foi enviada com sucesso!");
        this.name = this.email = "";
        return true;
      }
    },
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
img {
  position: absolute;
  width: 100%;
  bottom: 0;
}
input {
  width: 100%;
  background: #ffffff;
  box-shadow: 0px 10px 15px 5px rgba(216, 216, 216, 0.25);
  border-radius: 30px;
}
button {
  width: 100%;
  background-color: white;
  color: black;
  box-shadow: 0px 10px 15px 5px rgba(216, 216, 216, 0.25);
}
::placeholder {
  font-size: 18px;
}
.background {
  width: 60%;
  height: 100%;
  background: whitesmoke;
  box-shadow: 0px 10px 15px 5px rgba(216, 216, 216, 0.25);
  margin-top: 10%;
  border-radius: 10px;
}
.zoomIn {
  -webkit-animation-name: zoomIn;
  animation-name: zoomIn;
  -webkit-animation-duration: 1s;
  animation-duration: 1s;
  -webkit-animation-fill-mode: both;
  animation-fill-mode: both;
}
@-webkit-keyframes zoomIn {
  0% {
    opacity: 0;
    -webkit-transform: scale3d(0.3, 0.3, 0.3);
    transform: scale3d(0.3, 0.3, 0.3);
  }
  50% {
    opacity: 1;
  }
}
@keyframes zoomIn {
  0% {
    opacity: 0;
    -webkit-transform: scale3d(0.3, 0.3, 0.3);
    transform: scale3d(0.3, 0.3, 0.3);
  }
  50% {
    opacity: 1;
  }
}
@media only screen and (max-width: 1280px) {
  .background {
    margin-top: 5px;
  }
  img {
    display: none;
  }
  h3 {
    font-size: 45px;
  }
}
@media only screen and (max-width: 600px) {
.background {
  width: 100%;
  height: 100%;
  margin-top: 20%;
}
  h3 {
    font-size: 50px;
  }
}
@media only screen and (max-width: 500px) {
  h3 {
    font-size: 30px;
  }
}
</style>
