<template>
  <div class="home">
    <h1 style="height: 850px">HomePage</h1>
    <v-btn @click="showPopup" elevation="2" raised rounded style="color: aqua"
      >Add Card</v-btn
    >
    <div class="test1" v-if="!show"></div>
    <div class="test2" v-else>
      <v-card
        style="width: 250px;height: 250px;position: fixed;top: 50%;right: 50%"
      >
        Test-card
        <v-btn @click="closePopup">Close</v-btn>
      </v-card>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  data: function() {
    return {
      show: false
    };
  },
  methods: {
    showPopup() {
      this.show = true;
    },
    closePopup(){
      this.show = false;
    }
  }
};
</script>
