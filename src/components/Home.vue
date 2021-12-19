<template>
  <div class="home">
    Basic switch component
    <div class="parent">
      <SwitchBtn class="switch-btn" :value="false" v-model="switchBtnValue" />
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
    switchBtnValue() {
      console.log(this.switchBtnValue);
    }
  },
  data() {
    return {
      switchBtnValue: false
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
}
</style>