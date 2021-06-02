<template>
  <div onload="loadImage()" class="text-center mt-5 d-flex">
    <b-container class="bv-example-row mb-3">
      <div class="d-flex flex-row-wrap container">
        <img :src="imageAvatar" alt="Avatar" class="rounded-circle mobile-img" />
        <h1 class="display-5">Marcio Lacerda</h1>
      </div>
      <b-row cols="3">
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left">❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
            <b-card-text class="float-left"> ❤ Lorem Picsum </b-card-text>
          </b-card>
        </b-col>
        <b-col class="mb-4 mt-4">
          <b-card :img-src="image" img-alt="Card image">
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
@media only screen and (max-width: 600px) {
  .mobile-img {
    width: 300px;
    height: 150px;
  }
  h1 {
    margin-top: 35px;
    margin-left: 10px;
    font-size: 25px;
  }
}
</style>
