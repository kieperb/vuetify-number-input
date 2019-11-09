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
          :value="bla"
          v-on:emitnumber="bla=$event"
        ></NumberInput>

        App: {{bla}} (is a {{typeof bla}})
        <NumberInput label="NumberInput"></NumberInput>

        <NumberInput placeholder="Placeholder" label="NumberInput"></NumberInput>

        <NumberInput label="Solo" solo></NumberInput>

        <NumberInput label="Solo" placeholder="Placeholder" solo></NumberInput>

        <NumberInput label="Filled" filled></NumberInput>

        <NumberInput label="Filled" placeholder="Placeholder" filled></NumberInput>

        <NumberInput label="Outlined" outlined></NumberInput>

        <NumberInput style label="Outlined" placeholder="Placeholder" outlined></NumberInput>
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

