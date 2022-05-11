<template>
  <div class="navbar">
    <!-- <div class="navbar-container">
      <div class="navbar-wrapper"> -->
    <div class="navbar-navigation">
      <router-link to="/">
        <Cleaning-Icons />
      </router-link>
      <div
        class="switch-btn"
        :class="{ 'switch-on': star !== null }"
        @click="switchTo"
      ></div>
      <ul class="navbar-nav">
        <li
          class="navbar-items"
          v-bind:style="activeClass"
          v-for="(item, index) in navBar"
          :key="index"
        >
          <router-link class="navbar-item" to="/" @click="foo(index)">{{
            item.name
          }}</router-link>
        </li>
      </ul>
    </div>

    <div class="navbar-right"></div>
    <div class="navbar-left"></div>
    <!-- </div>
    </div> -->
  </div>
</template>

<script>
import { navBar } from "@/helpers/navbar.js";
import CleaningIcons from "@/components/Icons/Cleaning.vue";
export default {
  components: {
    CleaningIcons,
  },
  data() {
    return {
      star: null,
      navBar,
      activeClass: {
        borderLeft: `2px solid #990`,
      },

      //  :class="{ 'border-left': 6 + 'px' + 'solid' + '#908' === item[5] }"
    };
  },
  computed: {},
  methods: {
    foo(index) {
      console.log(index);
    },
    switchTo() {
      if (this.star === null) {
        this.star = true;
      } else {
        this.star = null;
      }
    },
  },
  mounted() {
    // this.$refs["extra"][5].style.display = "none";
    // console.log(this.$refs["extra"][5]);
  },
};
</script>

<style lang="scss">
@import "@/assets/styles/styles.scss";
.navbar {
  display: flex;
  justify-content: center;
  max-width: 1340px;
  &-navigation {
    display: inline-flex;
    width: 100%;
  }
  &-nav {
    display: inline-flex;
    width: 100%;
    align-items: center;
  }
  &-items {
    display: inline-flex;
    justify-content: center;
    flex-shrink: 1;
    flex-grow: 1;
  }
  &-item {
    letter-spacing: 0.2px;
    font-family: "TTTravelsMedium";
    color: #404040;
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 120%;
  }
}
.extra {
  border-left: 6px solid green;
}
</style>
