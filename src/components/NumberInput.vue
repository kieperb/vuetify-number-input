<template>
  <v-text-field
    :label="label"
    v-model="stringValue"
    :disabled="disabled"
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
    :prefix="prefix"
    :suffix="suffix"
    @keydown="isNumber($event)"
    v-on:blur="$emit('blur', $event.target.value)"
  ></v-text-field>
</template>

<script>
// todo rules prop
export default {
  name: "NumberInput",
  created: function() {
    if (typeof this.value !== "number") {
      if (typeof this.value === "string") {
        this.value = this.value.replace(",", ".");
        this.numberValue = isNaN(parseFloat(this.value))
          ? 0
          : parseFloat(this.value);
        this.value = this.numberValue;
      } else {
        this.value = 0;
        this.numberValue = 0;
      }
    } else {
      this.stringValue = this.value;
      this.numberValue = this.value;
    }
  },
  watch: {
    stringValue: function(val, oldval) {
      if (typeof val !== "number") {
        if (typeof val === "string") {
          val = val.replace(",", ".");
          const parsed = parseFloat(val);
          this.numberValue = isNaN(parsed) ? 0 : parsed;
        }
      } else {
        this.numberValue = val;
      }
      if (this.keyPressed == true && val != oldval) {
        this.$emit("input", this.numberValue);
        this.keyPressed = false;
      }
    },
    value: function(val, oldval) {
      if (typeof val !== "number") {
        if (typeof val === "string") {
          val = val.replace(",", ".");
        }
        const parsed = parseFloat(val);
        this.numberValue = isNaN(parsed) ? 0 : parsed;
      } else {
        this.numberValue = val;
      }
      if (this.numberValue != oldval) {
        this.stringValue = this.numberValue;
      }
    }
  },
  props: {
    prefix: String,
    suffix: String,
    min: {
      type: Number,
      default: 0
    },
    max: {
      type: Number
    },
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
    placeholder: {
      type: String,
      default: "0"
    },
    hint: String,
    disabled: {
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
    },
    rules: {
      type: Array
    }
  },
  data: function() {
    // todo Eingabebereich von / bis, runden,
    return {
      numberValue: 0,
      stringValue: "0",
      keyPressed: false
    };
  },
  methods: {
    isNumber: function(evt) {
      evt = evt ? evt : window.event;
      var charCode = evt.which ? evt.which : evt.keyCode;

      if (
        charCode > 31 &&
        (charCode < 48 || charCode > 57) && // zahlen
        (charCode < 96 || charCode > 105) && // zahlen
        charCode !== 46 && // .
        charCode !== 45 && // -
        charCode !== 44 && // ,
        charCode !== 110 &&
        charCode !== 189 &&
        charCode !== 109 &&
        charCode !== 37 && // arrow left
        charCode !== 39 && // arrow right
        charCode !== 190 &&
        charCode !== 86 && // v
        charCode !== 67 && // c
        charCode !== 17 && // strg
        charCode !== 188
      ) {
        evt.preventDefault();
      } else {
        this.keyPressed = true;
        return true;
      }
    }
  }
};
</script>
