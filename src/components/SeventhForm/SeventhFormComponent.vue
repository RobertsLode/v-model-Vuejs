<template>
  <div class="main--div">
    <div class="input--box">
      <SeventhtForm @changevisibilty="changeTitleSix" />
      <SeventhtFormOutput :visibility="visibility" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import SeventhtForm from "@/components/SeventhForm/SeventhForm.vue";
import SeventhtFormOutput from "@/components/SeventhForm/SeventhFormOutput.vue";

export default defineComponent({
  name: "FiftFormComponent",
  components: {
    SeventhtForm,
    SeventhtFormOutput,
  },
  data: () => ({
    visibility: "",
  }),

  computed: {},

  methods: {
    changeTitleSix(visibility: string) {
      this.visibility = visibility;
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
