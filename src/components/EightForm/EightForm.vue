<template>
  <div class="main--box">
    <label for="this">
      <span>Change visibility</span>
      <input
        id="this"
        type="checkbox"
        class="button"
        @change="visibilityHandler"
      />
    </label>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "EightForm",
  emits: ["changevisibilty"],
  data: () => ({
    visibilty: "visible",
  }),
  methods: {
    visibilityHandler() {
      if (this.visibilty === "visible") {
        this.$emit("changevisibilty", "hidden");

        this.visibilty = "hidden";
      } else {
        this.$emit("changevisibilty", "visible");

        this.visibilty = "visible";
      }
    },
  },
});
</script>
<style lang="scss">
.main--box {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
}

.button {
  min-height: 40px;
  background-color: transparent;
  border: none;
  background-color: rgb(231, 231, 231);
  &:hover {
    background-color: rgb(190, 190, 190);
    border-radius: 10px;
  }
}
</style>
