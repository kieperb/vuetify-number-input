<template>
  <div id="app">
    <v-form>
      <v-container>
        <NumberInput
          placeholder="0"
          hint="if empty value is 0"
          label="NumberInput"
          v-model="bla"
          v-on:emitnumber="bla = $event"
        ></NumberInput>

        <NumberInput v-model="bla" label="NumberInput"></NumberInput>

        <NumberInput
          v-model="bla"
          placeholder="Placeholder"
          label="NumberInput"
        ></NumberInput>

        <NumberInput v-model="bla" label="Solo" solo></NumberInput>

        <NumberInput
          v-model="bla"
          label="Solo"
          placeholder="Placeholder"
          solo
        ></NumberInput>

        <NumberInput v-model="bla" label="Filled" filled></NumberInput>

        <NumberInput
          v-model="bla"
          label="Filled"
          placeholder="Placeholder"
          filled
        ></NumberInput>
        App: {{ bla }} (is a {{ typeof bla }})
      </v-container>
    </v-form>
  </div>
</template>

<script>
import NumberInput from "./components/NumberInput";

export default {
  name: "App",
  components: {
    NumberInput,
  },
  data() {
    return {
      bla: 0,
    };
  },
};
</script>

