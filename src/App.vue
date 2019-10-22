<template>
  <div id="app">        
    <NumberInput v-model="bla"  />    
   
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
      bla: "4"
    }
  }
};
</script>

