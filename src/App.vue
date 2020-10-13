<template>
  <div id="app">
    <Navbar />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Navbar from "@/components/defaultApp/navbar";
import Footer from "@/components/defaultApp/footer";

export default {
  components: {
    Navbar,
    Footer
  }
};
</script>

<style></style>
