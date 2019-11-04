<template> 
  <v-text-field 
    :label="label" 
    v-model="value" 
    :dissabled="dissabled"
    :input="$emit('emitnumber', value)"
    
    
  ></v-text-field> 
</template>

<script>
export default {
  name: "NumberInput",
  created: function() {
    this.value = this.computedNumberValue;
  },
  watch: {
    value: function(val) {
      this.value = isNaN(parseFloat(val)) ? 0 : parseFloat(val);
    }
  },
  computed: {
    computedNumberValue: function() {
      return this.numberValue;
    }
  },
  props: {
    dissabled: Boolean,
    label: String,
    numberValue: Number
  },
  data() {
    return {
      value: 0
    };
  }
};
</script>
