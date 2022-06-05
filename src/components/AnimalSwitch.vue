<template>
  <div class="custom-control custom-switch">
    <label class="custom-control-label" for="customSwitch1">
      <input
        @click="toggleView"
        type="checkbox"
        class="custom-control-input"
        id="customSwitch1"
      />
      {{ viewMode === "all" ? "Show only dogs" : "Show All" }}
    </label>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";

export default defineComponent({
  name: "AnimalSwitch",
  props: ["viewMode", "toggleView"],
});
</script>

<style></style>
