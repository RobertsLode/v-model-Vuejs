<template>
  <div>
    <span>{{ title }}</span>
    <br />
    <span>{{ description }}</span>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "SixFormOutput",
  props: ["title", "description"],
});
</script>

<style lang="scss">
.box {
  width: 100px;
  height: 100px;
}
</style>
