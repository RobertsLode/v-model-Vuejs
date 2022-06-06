<template>
  <div class="main--div">
    <div class="input--box">
      <SixttForm
        @changeTitleSix="changeTitleSix"
        @changeDescriptionSix="changeDescriptionSix"
      />
      <SixtFormOutput :title="title" :description="description" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SixttForm from "@/components/SixtForm/SixtForm.vue";
import SixtFormOutput from "@/components/SixtForm/SixtFormOutput.vue";

export default defineComponent({
  name: "FiftFormComponent",
  components: {
    SixttForm,
    SixtFormOutput,
  },
  data: () => ({
    title: "",
    description: "",
  }),

  computed: {},

  methods: {
    changeTitleSix(title: string) {
      this.title = title;
    },
    changeDescriptionSix(description: string) {
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
