<template>
  <div class="menu-button-container" :style="styleItems">
    <button v-if="isRedirect" class="main-button menu-button">
      <a :href="redirectPath">{{ text }}</a>
    </button>
    <button v-else class="main-button menu-button">
      {{ text }}
    </button>
  </div>
</template>

<script>
export default {
  props: {
    text: {
      required: true,
      type: String,
      default: "",
    },
    isRedirect: {
      required: false,
      type: Boolean,
      default: false,
    },
    redirectPath: {
      required: false,
      type: String,
      default: "/",
    },
    styleItems: {
      required: false,
      type: String,
      default: "",
    },
  },
};
</script>

<style scoped>
.menu-button-container {
  width: 100%;
  text-align: center;
}
.main-button.menu-button {
  width: auto;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  font-family: "Permanent Marker";
  font-size: 1.5rem;
  padding: 7px 20px !important;
  border-radius: 5px;
  background-color: rgba(255, 255, 255, 0);
  border: 6px solid #f2e9e4;
  transition: 0.8s;
}

.main-button.menu-button a {
  text-decoration: none;
  color: #f2e9e4;
}

.main-button.menu-button:hover {
  background-color: black;
  cursor: pointer;
}
.main-button.menu-button:hover a {
  color: #f2e9e4;
}
</style>
