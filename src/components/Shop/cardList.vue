<template>
  <div>
    <v-card max-width="344" style="background: rgba(2,234,231,0.5)">
      <v-card-title>{{ card.name }}</v-card-title>
      <v-card-subtitle>Price: ${{ card.price }}</v-card-subtitle>
      <v-card-text>About:{{ card.description }}</v-card-text>

      <v-btn @click="buyNow" v-if="disableButton">Buy</v-btn>
      <v-btn v-on:click="$emit('removeCard', card.id)">Delete</v-btn>

      <div v-if="this.card.now - counter === 0">All Out</div>
      <div v-else-if="this.card.now - counter < 5">
        Left {{ this.card.now - counter }} !
      </div>
      <div v-else>Buy</div>

      <v-card-text>You Buy Now:{{ this.counter }}</v-card-text>
      <v-card-text>{{ card.now }}</v-card-text>
    </v-card>
  </div>
</template>

<script>

export default {
  data: function() {
    return {
      counter: 0,
      count: this.card.now
    };
  },
  props: ["card"],

  methods: {
    removeCard(id) {
      console.log(id);
    },
    buyNow() {
      this.counter++;
      if (this.card.now === this.counter) {
        this.disableButton();
      }
    },
    disableButton() {
      console.log('Disabled')
    }
  },
  filter() {

  }
};
</script>
