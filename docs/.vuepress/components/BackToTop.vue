<template>
  <transition name="fade">
    <svg
      v-if="show"
      class="go-to-top"
      @click="scrollToTop"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 49.484 28.284"
    >
      <g transform="translate(-229 -126.358)">
        <rect
          fill="currentColor"
          width="35"
          height="5"
          rx="2"
          transform="translate(229 151.107) rotate(-45)"
        />
        <rect
          fill="currentColor"
          width="35"
          height="5"
          rx="2"
          transform="translate(274.949 154.642) rotate(-135)"
        />
      </g>
    </svg>
  </transition>
</template>

<script>
import debounce from "lodash.debounce";

export default {
  props: {
    threshold: {
      type: Number,
      default: 300
    }
  },

  data() {
    return {
      scrollTop: null
    };
  },

  mounted() {
    this.scrollTop = this.getScrollTop();
    window.addEventListener(
      "scroll",
      debounce(() => {
        this.scrollTop = this.getScrollTop();
      }, 100)
    );
  },

  methods: {
    getScrollTop() {
      return (
        window.pageYOffset ||
        document.documentElement.scrollTop ||
        document.body.scrollTop ||
        0
      );
    },

    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" });
      this.scrollTop = 0;
    }
  },

  computed: {
    show() {
      return this.scrollTop > this.threshold;
    }
  }
};
</script>

<style scoped>
.go-to-top {
  cursor: pointer;
  position: fixed;
  bottom: 2rem;
  right: 2.5rem;
  width: 2rem;
  /* color: #72cda4; */
  color: red;
  z-index: 1;
}

.go-to-top:hover {
  color: #3eaf7c;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
