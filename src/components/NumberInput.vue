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
    persistentHint: {
      type: Boolean,
      default: false
    },
    counter: {
      type: Number,
      default: null
    },
    clearable: {
      type: Boolean,
      default: false
    },
    singleLine: {
      type: Boolean,
      default: false
    },
    outlined: {
      type: Boolean,
      default: false
    },
    filled: {
      type: Boolean,
      default: false
    },
    dense: {
      type: Boolean,
      default: false
    },
    solo: {
      type: Boolean,
      default: false
    },
    placeholder: String,
    hint: String,
    dissabled: {
      type: Boolean,
      default: false
    },
    label: String,
    value: {
      type: Number,
      default: 0
    },
    shaped: {
      type: Boolean,
      default: false
    },
    rounded: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      numberValue: 0
    };
  }
};
</script>