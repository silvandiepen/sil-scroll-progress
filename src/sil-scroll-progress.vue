<template>
  <div
    class="scrolled"
    :style="`--scrolled: ${scrolled}%; --scrolled-bg: ${backgroundColor}; --scrolled-height: ${height}; --scrolled-color: ${color}`"
  ></div>
</template>

<script>
export default {
  props: {
    height: {
      type: String,
      default: "3px"
    },
    backgroundColor: {
      type: String,
      default: "transparent"
    },
    color: {
      type: String,
      default: "black"
    }
  },
  data() {
    return {
      scrolled: 0
    };
  },
  mounted() {
    if (!process.server) {
      window.addEventListener("scroll", this.handleScroll);
    }
  },
  destroyed() {
    if (!process.server) {
      window.removeEventListener("scroll", this.handleScroll);
    }
  },
  methods: {
    handleScroll() {
      if (!process.server) {
        let h = document.documentElement;
        let b = document.body;
        let st = "scrollTop";
        let sh = "scrollHeight";

        this.scrolled =
          ((h[st] || b[st]) / ((h[sh] || b[sh]) - h.clientHeight)) * 100;
      }
    }
  }
};
</script>

<style scoped>
.scrolled {
  width: 100%;
  background-color: var(--scrolled-bg);
  height: var(--scrolled-height);
}
.scrolled:before {
  width: var(--scrolled, 50%);
  background-color: var(--scrolled-color);
  height: 100%;
  content: "";
  display: block;
}
</style>