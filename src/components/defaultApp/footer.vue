<template>
  <v-footer dark padless>
    <v-row
      style="display: flex; justify-content: center;width: 100%"
      no-gutters
    >
      <v-btn
        v-for="link in links"
        :key="link.id"
        :to="link.path"
        color="white"
        text
        rounded
        class="my-2"
      >
        {{ link.name }}
      </v-btn>
      <v-col style="text-align: center" class="" cols="12">
        {{ new Date().getFullYear() }} — <strong>TestVue</strong>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    links: [
      {
        id:"1",
        name: "Home",
        path: "/"
      },
      {
        id:"2",
        name: "About",
        path: "/About"
      }
    ]
  })
};
</script>
