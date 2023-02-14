<template>
  <div class="button">
    <button class="duplicator" @click="duplicateCard">Duplicate Card</button>
    <button class="toggle-background" @click="toggleBackground">Toggle Background</button>
    <button class="change-heading" @click="changeHeading">Change Heading</button>
    <button class="delete-card" @click="deleteCard">Delete Card</button>
  </div>
  <div id="card" :class="{ 'card': true, 'bg-toggled': isBackgroundToggled }">
    <h1>{{ heading }}</h1>
    <img src="https://www.psu.edu/psu-edu-assets/images/shared/psu-mark.svg" alt="The Penn State Logo">
    <p :class="detailsClass">This is the logo that The Pennsylvania State University uses.</p>
    <button class="details" @click="toggleDetails">Toggle Details</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      heading: 'The Penn State Logo',
      isDetailsVisible: false,
      isBackgroundToggled: false
    };
  },
  methods: {
    duplicateCard() {
      const newCard = document.getElementById('card').cloneNode(true);
      document.body.appendChild(newCard);
    },
    toggleBackground() {
      this.isBackgroundToggled = !this.isBackgroundToggled;
    },
    changeHeading() {
      this.heading = 'The Pennsylvania State University Logo';
    },
    deleteCard() {
      const card = document.getElementById('card');
      card.parentNode.removeChild(card);
    },
    toggleDetails() {
      this.isDetailsVisible = !this.isDetailsVisible;
    }
  },
  computed: {
    detailsClass() {
      return this.isDetailsVisible ? '' : 'hidden';
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.duplicator:hover,
.duplicator:focus {
  background-color: green;
}

.card {
  width: 350px;
  border: 2px solid black;
  text-align: center;
  margin: 0 auto;
  margin-bottom: 16px;
}

h1 {
  margin-top: 8px;
  margin-left: 32px;
  margin-right: 32px;
}

img {
  display: block;
  margin: 16px auto;
  width: 400px;
}

p {
  margin-top: 16px;
  margin-bottom: 32px;
  display: none;
}

.details {
  margin-bottom: 8px;
  border: 2px solid black;
  background-color: gray;
  color: blue;
}

@media only screen and (min-width: 500px) and (max-width: 800px) {
  .button {
    display: none;
  }
}

@media only screen and (max-width: 500px) {
  .card {
    transform: scale(0.8);
  }

  img {
    width: 80%;
  }
}

.bg-toggled {
  background-color: green;
}

.hidden {
  display: block;
}
</style>