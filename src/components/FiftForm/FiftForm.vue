<template>
  <div class="main--box">
    <input
      class="input"
      minlength="2"
      required
      type="text"
      v-model="inputValueOne"
    />
    <button @click="titleHandler" class="button" type="submit">Change</button>
    <input
      class="input"
      minlength="2"
      required
      type="text"
      v-model="inputValueTwo"
    />
    <button @click="descriptionHandler" class="button" type="submit">
      Change
    </button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "FirftForm",
  emits: ["changeTitleFive", "changeDescriptionFive"],
  data: () => ({
    inputValueOne: "",
    inputValueTwo: "",
  }),
  methods: {
    titleHandler() {
      this.$emit("changeTitleFive", this.inputValueOne);

      this.inputValueOne = "";
    },
    descriptionHandler() {
      this.$emit("changeDescriptionFive", this.inputValueTwo);

      this.inputValueTwo = "";
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

.form {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  gap: 6px;
}

.input {
  min-height: 40px;
  min-width: 300px;
  border: none;
  border-bottom: 4px solid rgb(190, 190, 190);
  &:focus {
    outline: none;
    background-color: rgb(190, 190, 190);
  }
}

.select {
  border: none;
  outline: none;
  min-height: 40px;
}
select:focus {
  outline: none;
  background-color: rgb(190, 190, 190);
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
