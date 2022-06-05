<template>
  <div class="main--box">
    <form class="form" @submit.prevent="submitHandler">
      <input
        class="input"
        minlength="2"
        required
        type="text"
        v-model="inputValue"
      />
      <select class="select" required v-model="selectValue">
        <option selected disabled value="">Select Dog or Cat!</option>
        <option value="Dog">Dog</option>
        <option value="Cat">Cat</option>
      </select>
      <button class="button" type="submit">Add animal</button>
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { v4 as uuidv4 } from "uuid";
export default defineComponent({
  name: "AnimalAdder",
  emits: ["addAnimal"],
  data: () => ({
    inputValue: "",
    selectValue: "",
  }),
  methods: {
    submitHandler() {
      const newAnimal = {
        name: this.inputValue,
        type: this.selectValue,
        id: uuidv4(),
      };

      this.$emit("addAnimal", newAnimal);
      this.selectValue = "";
      this.inputValue = "";
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
