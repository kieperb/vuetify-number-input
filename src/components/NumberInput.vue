<template>
  <div >
    <v-text-field    
     v-bind:value="value"     
    ></v-text-field>
 
  <br>
  NumberinputValue: {{value}}
  </div>
</template>

<script>
export default {
  name: "NumberInput",
  watch: {
    value: function (val) {
      this.value = isNaN(parseFloat(val)) ? 0 : parseFloat(val);     
    }
  },
  props: {
    numberValue: String
  },
  data() {
    return {
      value: 5
    }
  }
};
</script>
