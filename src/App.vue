<template>
  <div id="app">        
    <NumberInput :numberValue="bla" v-on:emitnumber="bla=$event" />   
    App: {{bla}}     
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
      bla: "2"
    }
  }
};
</script>

