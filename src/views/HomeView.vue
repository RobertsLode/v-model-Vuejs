<template>
  <div class="main--div">
    <div class="input--box">
      <span>{{ inputOne }}</span>
      <FirstForm @changeTitleOne="changeTitleOne" />
    </div>
    <br /><br />
    <div class="input--box">
      <span>{{ inputTwo }}</span>
      <SecondForm @changeTitleTwo="changeTitleTwo" />
    </div>
    <br /><br />
    <div class="input--box">
      <ThirdForm @changeTitleThree="changeTitleThree" />
      <ThirdFormOutput :inputThree="inputThree" />
    </div>
    <div class="input--box">
      <FourthForm @changeTitleFour="changeTitleFour" />
      <FourthFormOutput :inputFour="inputFour" />
    </div>
    <div class="input--box">
      <FiftFormComponentVue />
    </div>
    <div class="input--box">
      <SixtFormComponentVue />
    </div>
    <div class="input--box">
      <SeventhFormComponentVue />
    </div>
    <div class="input--box">
      <EightFormComponentVue />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import FirstForm from "@/components/FirstForm.vue";
import SecondForm from "@/components/SecondForm.vue";
import ThirdForm from "@/components/ThirdForm.vue";
import ThirdFormOutput from "@/components/ThirdFormOutput.vue";
import FourthForm from "@/components/FourthForm.vue";
import FourthFormOutput from "@/components/FourthFormOutput.vue";
import FiftFormComponentVue from "@/components/FiftForm/FiftFormComponent.vue";
import SixtFormComponentVue from "@/components/SixtForm/SixtFormComponent.vue";
import SeventhFormComponentVue from "@/components/SeventhForm/SeventhFormComponent.vue";
import EightFormComponentVue from "@/components/EightForm/EightFormComponent.vue";

export default defineComponent({
  name: "HomeView",
  components: {
    FirstForm,
    SecondForm,
    ThirdForm,
    ThirdFormOutput,
    FourthForm,
    FourthFormOutput,
    FiftFormComponentVue,
    SixtFormComponentVue,
    SeventhFormComponentVue,
    EightFormComponentVue,
  },
  data: () => ({
    inputOne: "",
    inputTwo: "",
    inputThree: "",
    inputFour: "",
  }),

  computed: {},

  methods: {
    changeTitleOne(title: string) {
      this.inputOne = title;
    },
    changeTitleTwo(title: string) {
      this.inputTwo = title;
    },
    changeTitleThree(title: string) {
      this.inputThree = title;
    },
    changeTitleFour(title: string) {
      this.inputFour = title;
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
  flex-wrap: wrap;
  gap: 30px;
}
.input--box {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  border: 1px solid black;
  widows: 100%;
}
</style>
