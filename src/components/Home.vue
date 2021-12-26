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
        <div class="state">State: {{ switchBtnValuesm }}</div>
      </div>
      <div class="example-large">
        Large
        <SwitchBtn
          class="switch-btn"
          :value="false"
          v-model="switchBtnValuelg"
          size="lg"
        />
        <div class="state">State: {{ switchBtnValuelg }}</div>
      </div>
    </div>

    <div class="colorParent">
      Color Prop
      <div class="colorChildren">
        <div class="color1">
          <SwitchBtn
            class="switch-btn"
            :value="false"
            v-model="switchBtnValueColor1"
            size="sm"
            color="#fabb41"
          />
          State: {{ switchBtnValueColor1 }}
        </div>

        <div class="color2">
          <SwitchBtn
            class="switch-btn"
            :value="false"
            v-model="switchBtnValueColor2"
            size="lg"
            color="#fb4044"
          />
          State: {{ switchBtnValueColor2 }}
        </div>
        <div class="color3">
          <SwitchBtn
            class="switch-btn"
            :value="false"
            v-model="switchBtnValueColor3"
            size="lg"
            color="#B945FF"
          />
          State: {{ switchBtnValueColor3 }}
        </div>
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
      switchBtnValuelg: false,
      switchBtnValueColor1: false,
      switchBtnValueColor2: false,
      switchBtnValueColor3: false
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
.colorParent {
  margin-top: 40px;
  width: 30%;
}
.colorChildren {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 100px;
}
.state {
  margin-top: 10px;
}
.example-large {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 80px;
}
.example-small {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 80px;
}

.color1 {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.color2 {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.color3 {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.color1 .switch-btn {
  margin-bottom: 15px;
}
.color2 .switch-btn {
  margin-bottom: 15px;
}
.color3 .switch-btn {
  margin-bottom: 15px;
}
@media only screen and (max-width: 1000px) {
  .parent {
    width: 100%;
  }
  .colorParent {
    width: 100%;
  }
}
</style>
