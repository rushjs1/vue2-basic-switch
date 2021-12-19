<template>
  <div class="home">
    Basic switch component
    <div class="parent">
      <div class="example-small">
        Small
        <SwitchBtn
          class="switch-btn"
          :value="false"
          v-model="switchBtnValuesm"
        />
      </div>
      <div class="example-large">
        Large
        <SwitchBtn
          class="switch-btn"
          :value="false"
          v-model="switchBtnValuelg"
          size="lg"
        />
      </div>
    </div>
  </div>
</template>

<script>
import SwitchBtn from "./customComponents/SwitchBtn";
export default {
  name: "Home",
  components: {
    SwitchBtn
  },
  watch: {
    switchBtnValuesm() {
      console.log("SwitchBtn-sm: " + this.switchBtnValuesm);
    },
    switchBtnValuelg() {
      console.log("SwitchBtn-lg: " + this.switchBtnValuelg);
    }
  },
  data() {
    return {
      switchBtnValuesm: false,
      switchBtnValuelg: false
    };
  }
};
</script>

<style>
.home {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
  height: 100%;
}
.parent {
  margin-top: 3%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  width: 30%;
}
</style>
