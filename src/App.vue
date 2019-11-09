<template>
  <div id="app">
    <v-form>
      <v-container>
        <v-row>
          <NumberInput
            solo
            dense
            placeholder="0"
            hint="if empty value is 0"
            label="NumberInput"
            :value="bla"
            v-on:emitnumber="bla=$event"
          />
        </v-row>
        <v-row>App: {{bla}} (is a {{typeof bla}})</v-row>
        <v-row>
          <v-col cols="12" sm="6" md="3">
            <NumberInput label="NumberInput"></NumberInput>
          </v-col>
          <v-col cols="12" sm="6" md="3">
            <NumberInput placeholder="Placeholder" label="NumberInput"></NumberInput>
          </v-col>

          <v-col cols="12" sm="6" md="3">
            <NumberInput label="Solo" solo></NumberInput>
          </v-col>
          <v-col cols="12" sm="6" md="3">
            <NumberInput label="Solo" placeholder="Placeholder" solo></NumberInput>
          </v-col>

          <v-col cols="12" sm="6" md="3">
            <NumberInput label="Filled" filled></NumberInput>
          </v-col>
          <v-col cols="12" sm="6" md="3">
            <NumberInput label="Filled" placeholder="Placeholder" filled></NumberInput>
          </v-col>

          <v-col cols="12" sm="6" md="3">
            <NumberInput label="Outlined" outlined></NumberInput>
          </v-col>
          <v-col cols="12" sm="6" md="3">
            <NumberInput label="Outlined" placeholder="Placeholder" outlined></NumberInput>
          </v-col>
        </v-row>
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

