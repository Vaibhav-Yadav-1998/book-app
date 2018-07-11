<template>
  <div id="app">
    <app-header/>
    <router-view/>
  </div>
</template>

<script>
import AppHeader from "@/components/AppHeader";
export default {
  components: {
    "app-header": AppHeader
  }
};
</script>


<style>
@import url("./assets/style.min.css");
@import url("https://fonts.googleapis.com/css?family=Lobster");
</style>
