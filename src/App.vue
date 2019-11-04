<template>
  <div id="app">
    <v-form>
      <v-container>
        <NumberInput
          solo
          dense
          placeholder="0"
          hint="if empty value is 0"
          label="NumberInput"
          :numberValue="bla"
          v-on:emitnumber="bla=$event"
        />
        App: {{bla}} (is a {{typeof bla}})
      </v-container>
    </v-form>
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

