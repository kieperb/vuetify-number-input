<template>
  <div>
    <v-text-field v-model="value" :input="$emit('emitnumber', value)"></v-text-field>
  </div>
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
    numberValue: Number
  },
  data() {
    return {
      value: 0
    };
  }
};
</script>
