<template>
  <div class="text-center mt-5 d-flex">
    <b-container class="bv-example-row mb-3">
      <div class="d-flex flex-row-wrap container">
        <img
          :src="imageAvatar"
          alt="Avatar"
          class="rounded-circle mobile-img"
        />
        <ul>
          <li><h1 class="display-5">Marcio Lacerda</h1></li>
          <li>
            <p><em>Developer from Matão-SP, Brazil</em></p>
          </li>
        </ul>
      </div>
      <b-row class="mobile-text">
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" class="imagem mb-5" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import image from "../assets/teste.jpg";
import imageAvatar from "../assets/avatar.jpg";

export default {
  data: function () {
    return {
      image: image,
      imageAvatar,
    };
  },
};
</script>

<style scoped>
.mobile-img {
  width: 150px;
  height: 150px;
}
li {
  list-style: none;
}
.imagem {
  width: 250px;
}
@media only screen and (max-width: 600px) {
  .mobile-img {
    width: 100px;
    height: 100px;
  }
  .imagem {
    width: 330px;
  }
  .mobile-text {
    margin-left: 10px;
    flex-direction: column;
  }
  h1 {
    margin-top: 10px;
    margin-left: 10px;
    font-size: 20px;
  }
}
</style>
