<template>
  <div class="main--box">
    <input
      class="input"
      minlength="2"
      required
      type="text"
      v-model="inputValue"
      v-on:input="submitHandler"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "forthForm",
  emits: ["changeTitleFour"],
  data: () => ({
    inputValue: "",
  }),
  methods: {
    submitHandler() {
      this.$emit("changeTitleFour", this.inputValue);
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
