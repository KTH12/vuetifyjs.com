<template>
  <v-form>
    <v-container>
      <v-layout row wrap>

        <v-flex xs12 sm6>
          <v-text-field
            v-model="title"
            :rules="rules"
            counter="25"
            label="Regular"
          ></v-text-field>
        </v-flex>

        <v-flex xs12 sm6>
          <v-text-field
            v-model="title"
            :rules="rules"
            counter="25"
            box
            label="Box"
          ></v-text-field>
        </v-flex>

        <v-flex xs12 sm6>
          <v-text-field
            v-model="title"
            :rules="rules"
            counter="25"
            label="Outline"
            outline
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
        title: 'Preliminary report',
        rules: [v => v.length <= 25 || 'Max 25 characters']
      }
    }
  }
</script>
