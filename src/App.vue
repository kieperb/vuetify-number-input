<template>
  <div id="app">
    <NumberInput label="NumberInput" :numberValue="bla" v-on:emitnumber="bla=$event"/>
    App: {{bla}} (is a {{typeof bla}})
  </div>
</template>

<script>
import NumberInput from "./components/NumberInput";

export default {
  name: "App",
  components: {
    NumberInput
  },
  data() {
    return {
      bla: 0
    };
  }
};
</script>

