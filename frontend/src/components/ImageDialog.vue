<template>
    <div class="text-center">
      <v-dialog :value="dialog" @input="updateDialog" width="auto">
        <v-card>
          <v-card-text>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
          </v-card-text>
          <v-card-actions>
            <v-btn color="primary" block @click="closeDialog">Close Dialog</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      dialog: Boolean,
    },
    methods: {
        closeDialog() {
    console.log("dialog hijo " + this.dialog);
    this.$emit("update:modelValue", false);
  },
      updateDialog(value) {
        this.$emit("update:modelValue", value);
      },
    },
  };
  </script>
  
  <style>
    
  </style>
