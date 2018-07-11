<template>
  <div class="home">
    <welcome-component msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Welcome from "@/components/Welcome.vue";

export default {
  name: "home",
  components: {
    "welcome-component": Welcome
  }
};
</script>
