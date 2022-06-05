<template>
  <div class="pion" :class="'pion-' + color">
    <div
      class="circles-inside"
      :style="
        color === 'black' ? 'border: 4px white double;' : 'border: 4px black double;'
      "
    ></div>
  </div>
</template>

<script lang="ts">
export default {
  name: "pion",
  props: {
    color: {
      type: String,
      default: "white",
    },
  },
};
</script>
<style scoped>
.pion {
  width: 60px;
  height: 60px;
  border: none;
  border-radius: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.circles-inside {
  width: 45px;
  height: 45px;
  border-radius: 45px;
}

.pion-black {
  background-color: black;
}
.pion-white {
  background-color: white;
}
</style>
