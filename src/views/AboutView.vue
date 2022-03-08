<template>
  <v-form>
    <v-container>
      <v-row>
        <v-col cols="12" md="4">
          <v-text-field
            ref="name"
            label="Name"
            placeholder="Untitled"
          ></v-text-field>
        </v-col>
        <v-col cols="12" md="4">
          <v-text-field
            ref="notes"
            label="Notes"
            placeholder="How did it go?"
          ></v-text-field
        ></v-col>
        <v-col cols="12" md="4">
          <v-select
            v-model="select"
            label="Activity Type"
            :items="items"
            item-text="runType"
          ></v-select>
        </v-col>
        <v-col cols="12" md="4">
          <v-text-field v-model="this.currentDate" label="Date"></v-text-field>
        </v-col>
        <v-col cols="12" md="4">
          <v-text-field
            v-model="this.currentTime"
            label="Time of Day"
          ></v-text-field>
        </v-col>
      </v-row>
      <v-btn @click="clear" color="primary">Clear</v-btn>
      <v-btn color="primary" class="float">Save</v-btn>
    </v-container>
  </v-form>
</template>
<script>
export default {
  data() {
    return {
      currentDate: new Date().toLocaleDateString(),
      currentTime: new Date().toLocaleTimeString(),
      select: { state: "Running" },
      items: [
        { runType: "Indoor Running" },
        { runType: "Street Running" },
        { runType: "Track Running" },
        { runType: "Trail Running" },
        { runType: "Treadmill Running" },
      ],
    };
  },
  methods: {
    clear() {
      this.$refs["name"].value = "";
      this.$refs["notes"].value = "";
      this.select = "";
    },
  },
};
</script>
<style>
.float {
  float: right;
}
</style>
