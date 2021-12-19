<template>
  <div class="switch">
    <div
      ref="switchBtn"
      :class="!this.toggle ? 'switch-btn-false' : 'switch-btn-true'"
      @click="changeValue"
    >
      <div :class="!this.toggle ? 'ball-false' : 'ball-true'"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SwitchBtn",
  components: {},
  props: {
    value: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      toggle: this.value
    };
  },
  methods: {
    changeValue() {
      this.toggle = !this.toggle;
      this.$emit("input", this.toggle);
    }
  }
};
</script>

<style>
.switch-btn-false {
  background-color: transparent;
  border-radius: 7px;
  width: 25px;
  display: flex;
  justify-content: flex-start;
  transition: 0.3s;
  border: 1px solid #c4c4c4;
  height: 14px;
  align-items: center;

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}
.ball-false {
  background-color: #c4c4c4;
  border-radius: 50px;
  width: 10px;
  height: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 1px;

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}
.switch-btn-true {
  background-color: dodgerblue;
  border-radius: 7px;
  width: 25px;
  display: flex;
  justify-content: flex-end;
  transition: 0.3s;
  height: 14px;
  align-items: center;
  border: 2px solid rgb(30, 144, 255);
  box-shadow: 0px 0px 0px 1.75px rgba(83, 169, 245, 0.7);

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}

.ball-true {
  background-color: #ffffff;
  border-radius: 50px;
  width: 10px;
  height: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 1px;

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}

.switch-btn-false:hover {
  cursor: pointer;
}
.switch-btn-true:hover {
  cursor: pointer;
}
</style>

