<template>
  <div class="switch">
    <div
      ref="switchBtn"
      :style="
        !this.toggle
          ? {
              'background-color': falseSwitchColor
            }
          : cssVars
      "
      :class="
        !this.toggle
          ? `switch-btn-false-${this.size}`
          : `switch-btn-true-${this.size}`
      "
      @click="changeValue"
    >
      <div
        ref="ball"
        :class="
          !this.toggle ? `ball-false-${this.size}` : `ball-true-${this.size}`
        "
      ></div>
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
    },
    size: {
      type: String,
      default: "sm"
    },
    color: {
      type: String,
      default: "#1e90ff"
    }
  },
  data() {
    return {
      toggle: this.value,
      sizeValue: this.size,
      falseBallColor: "#a2a2a2",
      falseSwitchColor: "#ffffff"
    };
  },
  computed: {
    cssVars() {
      return {
        "--bg-color": this.color
      };
    }
  },
  methods: {
    changeValue() {
      this.toggle = !this.toggle;
      this.$emit("input", this.toggle);
    }
  },
  mounted() {
    if (this.color != "#1e90ff") {
      this.$refs.switchBtn.style.boxShadow = "none";
    }
  }
};
</script>

<style>
.switch-btn-false-sm {
  background-color: transparent;
  border-radius: 7px;
  width: 25px;
  display: flex;
  justify-content: flex-start;
  transition: 0.3s;
  border: 1px;
  border-style: solid;
  border-color: #c4c4c4;

  height: 14px;
  align-items: center;

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}

.switch-btn-false-lg {
  background-color: transparent;
  border-radius: 15px;
  width: 45px;
  display: flex;
  justify-content: flex-start;
  transition: 0.3s;
  border: 2px solid #c4c4c4;
  height: 24px;
  align-items: center;

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}
.ball-false-sm {
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
.ball-false-lg {
  background-color: #c4c4c4;
  border-radius: 50px;
  width: 18px;
  height: 18px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 2px;

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}
.switch-btn-true-sm {
  background-color: dodgerblue;
  border-radius: 7px;
  width: 25px;
  display: flex;
  justify-content: flex-end;
  transition: 0.3s;
  height: 14px;
  align-items: center;
  box-shadow: 0px 0px 0px 1.75px rgba(83, 169, 245, 0.7);
  background-color: var(--bg-color);
  border: 2px solid var(--bg-color);

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}
.switch-btn-true-lg {
  border-radius: 15px;
  width: 45px;
  display: flex;
  justify-content: flex-end;
  transition: 0.3s;
  height: 24px;
  align-items: center;
  box-shadow: 0px 0px 0px 1.75px rgba(83, 169, 245, 0.7);
  background-color: var(--bg-color);
  border: 2px solid var(--bg-color);

  user-select: none; /* supported by Chrome and Opera */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
}

.ball-true-sm {
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
.ball-true-lg {
  background-color: #ffffff;
  border-radius: 50px;
  width: 18px;
  height: 18px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-right: 1px;
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
