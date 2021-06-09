<template>
<div>
  <div v-for="candidato in candidatos" v-bind:key="candidato.id">
    <v-card class="mx-auto my-5">
      <v-card-title>
        {{ candidato.id }}
        {{ candidato.name }}
      </v-card-title>

      <v-card-text>
        <div v-if="candidato.aresa === null">
          <p>Sem experiência anterior!!!</p>
        </div>
        <div v-else>
        <p> Experiência anterior: {{ JSON.parse(candidato.aresa[0]) }}</p>
        </div>
        <!-- {{ candidato.technologies }} -->
      <!-- {{ candidato.nome } placing a single v-spacer before or after the child components, the components will push to th} -->
      </v-card-text>

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
  }
</script>
