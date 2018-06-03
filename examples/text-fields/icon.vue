<template>
  <v-form>
    <v-container>
      <v-layout row wrap>

        <v-flex xs12 sm6>
          <v-text-field
            box
            label="Account name"
            prepend-icon="mdi-account-circle"
          ></v-text-field>
        </v-flex>

        <v-flex xs12 sm6>
          <v-text-field
            box
            label="Email address"
            append-outer-icon="mdi-at"
            hint="Valid Email address"
          ></v-text-field>
        </v-flex>

        <v-flex xs12 sm6>
          <v-text-field
            v-model="password"
            :rules="[v => !!v && v.length >= 6 || 'Password too short!']"
            :append-icon="show ? 'visibility_off' : 'visibility'"
            :append-icon-cb="showPassword"
            :type="show ? 'text' : 'password'"
            box
            hint="Password must be 6 characters long"
            label="Password"
            prepend-icon="mdi-textbox-password"
            validate-on-blur
          ></v-text-field>
        </v-flex>

        <v-flex xs12 sm6>
          <v-text-field
            v-model="message"
            :append-icon="marker ? 'mdi-map-marker' : 'mdi-map-marker-off'"
            :append-icon-cb="toggleMarker"
            :append-outer-icon="message ? 'mdi-message-processing' : 'mdi-message'"
            :clear-icon-cb="clearMessage"
            :prepend-icon="message ? 'mdi-send' : 'mdi-microphone'"
            :prepend-icon-cb="sendMessage"
            box
            clear-icon="mdi-close-circle"
            clearable
            label="Message"
            type="text"
          ></v-text-field>
        </v-flex>

      </v-layout>
    </v-container>
  </v-form>
</template>

<script>
  export default {
    data () {
      return {
        password: 'Password',
        show: false,
        message: 'Hey!',
        marker: true
      }
    },

    methods: {
      showPassword () {
        this.show = !this.show
      },
      toggleMarker () {
        this.marker = !this.marker
      },
      sendMessage () {
        // ...
        this.clearMessage()
      },
      clearMessage () {
        this.message = ''
      }
    }
  }
</script>
