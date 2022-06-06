<template>
  {{ visibility }}
  <div class="box" :style="{ visibility: visibility }"></div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "EightFormOutput",
  props: ["visibility"],
});
</script>

<style scoped lang="scss">
.box {
  width: 100px;
  height: 100px;
  background-color: orange;
  border: 1px solid black;
}
</style>
