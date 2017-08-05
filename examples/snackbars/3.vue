<template>
  <v-card class="grey lighten-4">
    <v-card-text>
      <v-container fluid>
        <v-layout row wrap>
          <v-flex xs12>
            <v-subheader
              :style="{ color: color ? 'black' : 'blue' }"                
              v-text="'This text can be either blue or black.'"
            ></v-subheader>
          </v-flex>
        </v-layout>
      </v-container>
      <v-btn block primary @click.native="snackbar = true" dark>Change text color</v-btn>
    </v-card-text>
    <v-snackbar
      v-model="snackbar"
      :timeoutFn="changeColor"
    >
      {{ text }}
      <v-btn dark flat @click.native="changeColor">Yes</v-btn>
      <v-btn dark flat @click.native="snackbar = false">No</v-btn>
    </v-snackbar>
  </v-card>
</template>

<script>
  export default {
    data () {
      return {
        snackbar: false,
        color: true,
        text: 'Are you sure you want to toggle text color?'
      }
    }
    methods : {
      changeColor () {
        this.snackbar = false
        this.color = !this.color
      }
    }
  }
</script>
