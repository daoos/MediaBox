<template>
  <div>
    <h1 style="margin-left: 8px">{{$t('Home')}}</h1>

    <v-btn
      v-for="item in items"
      v-bind:key="item.id"
      v-on:click="onItemClick(item.id)"
      class="ma-2"
      tile
      outlined
      color="primary"
    >
      <v-icon left>{{item.icon}}</v-icon>
      {{$t(`${item.text}`)}}
    </v-btn>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      { icon: "mdi-movie", text: "Movies", id: "movies" },
      { icon: "mdi-television", text: "Series", id: "series" },
      { icon: "mdi-settings", text: "Settings", id: "settings" }
    ]
  }),

  methods: {
    onItemClick(itemid) {
      if (!itemid) {
        return;
      }

      if (itemid == "movies") {
        return this.$router.push("/medialist/movies");
      }

      if (itemid == "series") {
        return this.$router.push("/medialist/series");
      }

      if (itemid == "settings") {
        return this.$router.push("/settings");
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
