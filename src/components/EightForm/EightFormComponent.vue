<template>
  <div class="main--div">
    <div class="input--box">
      <EightForm @changevisibilty="changevisibilty" />
      <EightFormOutput :visibility="visibility" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import EightForm from "@/components/EightForm/EightForm.vue";
import EightFormOutput from "@/components/EightForm/EightFormOutput.vue";

export default defineComponent({
  name: "FiftFormComponent",
  components: {
    EightForm,
    EightFormOutput,
  },
  data: () => ({
    visibility: "",
  }),

  computed: {},

  methods: {
    changevisibilty(visibility: string) {
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
