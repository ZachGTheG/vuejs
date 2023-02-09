<template>
  <h1>{{ msg }}</h1>

  <p>
    <a href="https://vitejs.dev/guide/features.html" target="_blank">
      Vite Documentation
    </a>
    |
    <a href="https://v3.vuejs.org/" target="_blank">Vue 3 Documentation</a>
  </p>

  <button type="button" @click="state.count++">count is: {{ state.count }}</button>
  <p>
    Edit
    <code>components/HelloWorld.vue</code> to test hot module replacement.
  </p>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })



duplicator()
{
  document.querySelector(".duplicator").addEventListener("click", function (e) {
    const node = document.getElementById("card");
    let clone = node.cloneNode(true);

    document.body.appendChild(clone);
  });
}

  const button = document.querySelector(".details");
  button.addEventListener("mouseenter", function () {
    button.style.backgroundColor = "green";
  });
  button.addEventListener("mouseleave", function () {
    button.style.backgroundColor = "";
  });

  const card = document.querySelector("#card");
  const toggleBackgroundButton = document.querySelector(".toggle-background");

  toggleBackgroundButton.addEventListener("click", function () {
    card.classList.toggle("bg-toggled");
  });

  const heading = document.querySelector("#card h1");
  const changeHeadingButton = document.querySelector(".change-heading");

  changeHeadingButton.addEventListener("click", function () {
    heading.textContent = "Something Else";
  });

  const cardContainer = document.querySelector("#card").parentNode;
  const deleteCardButton = document.querySelector(".delete-card");

  deleteCardButton.addEventListener("click", function () {
    cardContainer.removeChild(cardContainer.lastChild);
  });

  const description = document.querySelector("#card p");
  const detailsButton = document.querySelector(".details");

  detailsButton.addEventListener("click", function () {
    description.classList.toggle("hidden");
  });

</script>

<style scoped>
a {
  color: #42b983;
}
</style>
