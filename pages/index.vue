<template>
<div>
  <div v-for="candidato in candidatos" v-bind:key="candidato.id">
    <v-card class="mx-auto my-5">
      <v-card-title>
        {{ candidato.id }}
        {{ candidato.name }}
      </v-card-title>

      <v-card-actions>
        <v-btn
          nuxt
          color="deep-purple"
          :to="`/${candidato.id}`">
          Saiba mais sobre {{ candidato.name}}
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-spacer></v-spacer>
  </div>
</div>
</template>

<script>
import mockdata from  '../mockdata.json'

export default {
  computed: {
    candidatos() {
      return mockdata.candidatos
      },
    },
    filters: {
      pretty: function(value) {
        return JSON.stringify(JSON.parse(value), null, 2);
    },
  },
}
</script>
