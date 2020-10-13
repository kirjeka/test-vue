<template>
  <div id="shop">
    <v-btn @click="takeCard" style="color: greenyellow">take Card</v-btn>
    <cardBlock v-bind:cards="cards" v-on:removeCard="removeThisCard" />
  </div>
</template>

<script>
import Cards from "../Json/card.json";
import cardBlock from "../components/Shop/cardBlock";

export default {
  data: function() {
    return {
      cards: []
    };
  },
  components: {
    cardBlock
  },

  methods: {
    takeCard() {
      this.cards = Cards;
      console.log(this.cards);
    },
    deleteCard(id) {
      this.cards = this.cards.filter(t => t.id !== id);
    },
    removeThisCard(id) {
      if (this.cards.cardOne.id === id) {
        console.log("ok1");
      } else if (this.cards.cardTwo.id === id) {
        console.log("ok2");
      } else {
        console.log("ok3");
      }
    }
  },
  mounted() {}
};
</script>
