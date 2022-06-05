<template>
  <div class="animal--main-box">
    <div v-for="{ name, type, id } in animalsView" :key="id" class="animal">
      <div class="name-box">
        <h3>{{ name }}</h3>
      </div>
      <div class="box">
        <h3 class="animal--type">{{ type }}</h3>
        <button class="button" @click="removeAnimal(id)">Delete</button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "AniamlList",
  props: ["removeAnimal", "animalsView"],
});
</script>

<style scoped lang="scss">
.animal--main-box {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  flex-direction: column;
}
.animal {
  display: flex;
  align-items: center;
  gap: 10px;
  justify-content: center;
  width: 800px;
  outline: 3px solid rgb(202, 202, 202);
  padding: 5px;
}

.animal--type {
  display: flex;
  align-self: center;
  background-color: rgb(219, 219, 219);
  padding: 5px 10px;
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

.name-box {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  width: 100%;
  flex-wrap: wrap;
  font-size: larger;
}

.box {
  display: flex;
  gap: 50px;
}
</style>
