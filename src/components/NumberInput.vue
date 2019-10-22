<template>
  <div >
    <v-text-field    
     v-model="value"     
     :input="$emit('emitnumber', value)"
    ></v-text-field> 
  
  Value: {{value}}
  <br>
  numberValue: {{numberValue}}
  </div>
</template>

<script>
export default {
  name: "NumberInput",
  created: function () {
 this.value = this.blub;    
  },
  watch: {
    value: function (val) {
      this.value = isNaN(parseFloat(val)) ? 0 : parseFloat(val);  
       
    }    
  },
  computed: {
    blub: function () {
      return this.numberValue;
    }
  },
  props: {
    numberValue: String
  },
  data() {
    return {
      value: 7
    }
  }
};
</script>
