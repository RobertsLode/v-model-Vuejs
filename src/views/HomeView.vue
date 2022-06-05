<template>
  <div class="main--div">
    <AnimalAdder @addAnimal="addAnimal" />
    <br /><br />
    <AnimalSwitch :toggleView="toggleView" :viewMode="viewMode" />
    <div>
      <AnimalList :removeAnimal="removeAnimal" :animalsView="animalsView" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import AnimalAdder from "@/components/AnimalAdder.vue";
import AnimalSwitch from "@/components/AnimalSwitch.vue";
import AnimalList from "@/components/AnimalList.vue";
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap/dist/js/bootstrap.js";

type ViewMode = "all" | "dog";

type ListItem = {
  name: string;
  type: string;
  id: number;
};

export default defineComponent({
  name: "HomeView",
  components: {
    AnimalAdder,
    AnimalSwitch,
    AnimalList,
  },
  data: () => ({
    viewMode: "all" as ViewMode,
    animals: [] as ListItem[],
  }),

  created() {
    this.animals = JSON.parse(localStorage.getItem("animals") || "[]");
  },

  computed: {
    animalsView() {
      if (this.viewMode === "dog") {
        return this.animalsDog;
      }

      return this.animals;
    },
    animalsDog() {
      return this.animals.filter((animal) => animal.type === "Dog");
    },
  },

  methods: {
    toggleView() {
      if (this.viewMode === "all") {
        this.viewMode = "dog";
      } else {
        this.viewMode = "all";
      }
    },

    addAnimal(animal: ListItem) {
      const newAnimals = [...this.animals];

      newAnimals.push(animal);

      this.animals = newAnimals;
    },

    removeAnimal(id: number) {
      const newAnimals = [...this.animals];

      // newAnimals.splice(
      //   this.animals.findIndex((animal) => animal.id === id),
      //   1
      // );

      // this.animals = newAnimals;

      const a = newAnimals.filter((singleAnimal) => {
        return singleAnimal.id !== id;
      });

      this.animals = a;
    },
  },

  watch: {
    animals(newAnimals) {
      localStorage.setItem("animals", JSON.stringify(newAnimals));
    },
  },
});
</script>
<style scoped lang="scss">
.main--div {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
