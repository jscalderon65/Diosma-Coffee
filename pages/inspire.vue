<template>
  <div>
    <div style="height: 100vh; display: flex; flex-flow: column">
      <div class="cover" style="flex: 1"></div>
      <div style="flex: 1"></div>
    </div>
    <div style="height: 100vh; display: flex; flex-flow: column">
      <div class="cover" style="flex: 1"></div>
      <div style="flex: 1"></div>
    </div>
    <div style="height: 100vh; display: flex; flex-flow: column">
      <div class="cover" style="flex: 1"></div>
      <div style="flex: 1"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "InspirePage",
};
</script>
<style scoped>
.cover {
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("assets/Coffee.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  object-fit: cover;
}
</style>
