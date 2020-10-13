<template>
  <div>
    <cardList
      v-for="card in cards"
      :key="card.id"
      v-bind:card="card"
      v-on:removeCard="removeThisCard"
      disabled="false"
    />
  </div>
</template>

<script>
import cardList from "./cardList";
export default {
  data: function() {
    return {

    };
  },
  props: ["cards"],
  components: {
    cardList
  },
  methods: {
    removeCard(id) {
      console.log(id);
    },
    removeThisCard(id) {
      this.$emit('removeCard',id)
    }
  },
  mounted() {

  }
};
</script>
