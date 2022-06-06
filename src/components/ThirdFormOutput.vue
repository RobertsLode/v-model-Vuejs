<template>
  <div :style="{ backgroundColor: inputThree }" class="box"></div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ThirdFormOutput",
  props: ["inputThree"],
});
</script>

<style lang="scss">
.box {
  width: 100px;
  height: 100px;
}
</style>
