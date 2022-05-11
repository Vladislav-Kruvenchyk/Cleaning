<template>
  <div class="container">
    <NavBar />
  </div>
</template>

<script>
import NavBar from "@/components/NavBar/navBar.vue";
export default {
  name: "GlobalHome",
  components: { NavBar },
};
</script>

<style lang="scss">
@import "@/assets/styles/styles.scss";
.container {
  max-width: 1440px;
  margin: 0 auto;
}
</style>
