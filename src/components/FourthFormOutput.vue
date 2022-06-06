<template>
  <div :style="{ backgroundColor: inputFour }" class="box"></div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "FourthFormOutput",
  props: ["inputFour"],
});
</script>

<style lang="scss">
.box {
  width: 100px;
  height: 100px;
}
</style>
