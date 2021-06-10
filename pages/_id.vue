<template>
  <div>
    <!-- <h1>{{this.$route.params}}</h1> -->
   <v-card>

    <v-card-title>
    <h2>{{ candidato.name }}</h2>
    </v-card-title>

    <v-card-text>
    <div v-if="candidato">
      Aniversário:{{candidato.birthdate}}<br>

      <v-spacer></v-spacer>

      Email:{{candidato.email}}<br>

      <v-spacer></v-spacer>

      Gênero:
      <div style="display:inline;" v-if="candidato.gender == 'Genderfluid'">
      Gênero Fluido!!!
      </div>
      <div style="display:inline;" v-else-if="candidato.gender == 'Agender'">
      Agênero
      </div>
      <div style="display:inline;" v-else-if="candidato.gender == 'Male'">
      Masculino
      </div>
      <div style="display:inline;" v-else-if="candidato.gender == 'Female'">
      Feminino
      </div>
      <div style="display:inline;" v-else-if="candidato.gender == 'Bigender'">
      Binário
      </div>
      <div style="display:inline;" v-else-if="candidato.gender == 'Non-binary'">
      Não binário
      </div>
      <div style="display:inline;" v-else-if="candidato.gender == 'Genderqueer'">
      Gênero Queer
      </div>

      <v-spacer></v-spacer>

      Etnicidade:{{candidato.ethnicity}}<br>
      Telefone:{{candidato.phone}}<br>


      <div>
      <br>
      Áreas de atuação:
        <div v-if="!candidato['aresa'][0]['name']">
          Sem áreas de atuação conhecidas!
        </div>
        <div v-else v-for="key in candidato['aresa'].length">
          {{candidato['aresa'][key-1]['name']}}<br>
        </div>
      </div>
      <br>

      <div>
      Experiência anterio
      </div>

      Apresenta deficiência:
      <div  style="display:inline;" v-if="candidato.isDeficiency">
        SIM!
      </div>
      <div style="display:inline;" v-else>
        NÃO!
      </div>

    </div>
    </v-card-text>

  </v-card>
  </div>
</template>

<script>
import mockdata from  '../mockdata.json'

export default {
  // fetch(mockdata.candidatos[this.$route.params.id-1])
      // .then(res => res.json())
      // .then(data => console.log(data));
  computed: {
    candidato() {
      const jsonData = require('../mockdata.json');
      // retorno = JSON.parse(mockdata.candidatos[this.$route.params.id - 1]);
      return jsonData.candidatos[this.$route.params.id - 1];
      },
    }
  };

//   export default{
//       data() {
//         return mockdata.CONTENT;
//       },
//       async asyncData({ params }){
//         const id = params.id

//         return { id };
//   },
// }
</script>
