<template>
  <div onload="loadImage()" class="text-center mt-5 d-flex">
    <b-container class="bv-example-row mb-3">
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
import imageAvatar from "../assets/bob.gif";

export default {
  data: function () {
    return {
      image: image,
      imageAvatar,
    };
  },
};
</script>
