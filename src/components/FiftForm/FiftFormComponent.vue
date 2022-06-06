<template>
  <div class="main--div">
    <div class="input--box">
      <FirftForm
        @changeTitleFive="changeTitleFive"
        @changeDescriptionFive="changeDescriptionFive"
      />
      <FiftFormOutput :title="title" :description="description" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import FirftForm from "@/components/FiftForm/FiftForm.vue";
import FiftFormOutput from "@/components/FiftForm/FiftFormOutput.vue";

export default defineComponent({
  name: "FiftFormComponent",
  components: {
    FirftForm,
    FiftFormOutput,
  },
  data: () => ({
    title: "",
    description: "",
  }),

  computed: {},

  methods: {
    changeTitleFive(title: string) {
      this.title = title;
    },
    changeDescriptionFive(description: string) {
      this.description = description;
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
.input--box {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
</style>
