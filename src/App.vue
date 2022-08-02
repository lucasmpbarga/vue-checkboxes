<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" width="25%" />
    <Checkbox
      v-on:check-event="checkOption"
      id="green"
      name="green"
      :isChecked="valueIsChecked('green')"
    />
    <Checkbox
      v-on:check-event="checkOption"
      id="red"
      name="red"
      :isChecked="valueIsChecked('red')"
    />
    <Checkbox
      v-on:check-event="checkOption"
      id="blue"
      name="blue"
      :isChecked="valueIsChecked('blue')"
    />
    <Checkbox
      v-on:check-event="checkOption"
      id="yellow"
      name="yellow"
      :isChecked="valueIsChecked('yellow')"
    />
    <Checkbox
      v-on:check-event="checkOption"
      id="gray"
      name="gray"
      :isChecked="valueIsChecked('gray')"
    />
    <button @click="printCheckedValues">print my checked values</button>
  </div>
</template>

<script>
import Checkbox from "./components/Checkbox.vue";
import "vue-swatches/dist/vue-swatches.css";

export default {
  name: "App",
  components: {
    Checkbox,
  },
  data: () => ({
    checkeds: [],
  }),
  methods: {
    checkOption(option) {
      const optionInArray = this.valueIsChecked(option);

      if (optionInArray) {
        const index = this.checkeds.indexOf(option);

        this.checkeds.splice(index, 1);
      } else {
        this.checkeds.push(option);
      }
    },
    valueIsChecked(value) {
      return this.checkeds.includes(value);
    },
    printCheckedValues() {
      console.log(this.checkeds);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
