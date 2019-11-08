<template>
  <v-text-field
    :label="label"
    v-model="numberValue"
    :dissabled="dissabled"
    :input="$emit('emitnumber', numberValue)"
    :hint="hint"
    :placeholder="placeholder"
    :solo="solo"
    :dense="dense"
    :filled="filled"
    :outlined="outlined"
    :shaped="shaped"
    :rounded="rounded"
    :single-line="singleLine"
    :clearable="clearable"
    :persistent-hint="persistentHint"
    :counter="counter"
  ></v-text-field>
</template>

<script>
export default {
  name: "NumberInput",
  created: function() {
    this.numberValue = this.computedNumberValue;
  },
  watch: {
    numberValue: function(val) {
      this.numberValue = isNaN(parseFloat(val)) ? 0 : parseFloat(val);
    }
  },
  computed: {
    computedNumberValue: function() {
      return this.value;
    }
  },
  props: {
    persistentHint: Boolean,
    counter: Number,
    clearable: Boolean,
    singleLine: Boolean,
    outlined: Boolean,
    filled: Boolean,
    dense: Boolean,
    solo: Boolean,
    placeholder: String,
    hint: String,
    dissabled: Boolean,
    label: String,
    value: Number,
    shaped: Boolean,
    rounded: Boolean
  },
  data() {
    return {
      numberValue: 0
    };
  }
};
</script>
