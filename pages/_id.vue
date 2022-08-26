<template>
  <div>
    <v-card>
      <v-card-title>
        <h2>{{ candidato.name }}</h2>
      </v-card-title>

      <v-card-text>
        <div v-if="candidato">
          Aniversário:{{ candidato.birthdate }}<br />

          <v-spacer></v-spacer>

          Email:{{ candidato.email }}<br />

          <v-spacer></v-spacer>

          Gênero:
          <div style="display: inline" v-if="candidato.gender == 'Genderfluid'">
            Gênero Fluido!!!
          </div>
          <div
            style="display: inline"
            v-else-if="candidato.gender == 'Agender'"
          >
            Agênero
          </div>
          <div style="display: inline" v-else-if="candidato.gender == 'Male'">
            Masculino
          </div>
          <div style="display: inline" v-else-if="candidato.gender == 'Female'">
            Feminino
          </div>
          <div
            style="display: inline"
            v-else-if="candidato.gender == 'Bigender'"
          >
            Binário
          </div>
          <div
            style="display: inline"
            v-else-if="candidato.gender == 'Non-binary'"
          >
            Não binário
          </div>
          <div
            style="display: inline"
            v-else-if="candidato.gender == 'Genderqueer'"
          >
            Gênero Queer
          </div>

          <v-spacer></v-spacer>

          Etnicidade:{{ candidato.ethnicity }}<br />
          Telefone:{{ candidato.phone }}<br />

          <div>
            <br />
            Áreas de atuação:
            <div v-if="!candidato['aresa'][0]['name']">
              Sem áreas de atuação conhecidas!
            </div>
            <div v-else v-for="key in candidato['aresa'].length">
              <ul>
                <li>{{ candidato["aresa"][key - 1]["name"] }}</li>
              </ul>
            </div>
          </div>
          <br />

          Experiência(s) anterior(es):
          <ul>
            <div v-for="key in candidato['experiences'].length">
              <li>{{ candidato['experiences'][key - 1]['companyName'] }}</li>
            </div>
          </ul>
          <br />

          Tecnologias conhecidas:
            <div v-for="key in candidato['technologies'].length">
              <ul>
                <li>
                {{ candidato['technologies'][key - 1]['name'] }}
                </li>
                Nível:
                <div style="display: inline" v-if="candidato['technologies'][key - 1]['level'] == 'BASIC' ">
                  Básico
                </div>
                <div style="display: inline" v-else-if="candidato['technologies'][key - 1]['level'] == INTERMEDIARY ">
                  Intermediário
                </div>
                <div style="display: inline" v-else-if="candidato['technologies'][key - 1]['level'] == ADVANCED ">
                  Avançado
                </div>
              </li>
              </ul>
            </div>

            <br />

          Apresenta deficiência:
          <div style="display: inline" v-if="candidato.isDeficiency">SIM!</div>
          <div style="display: inline" v-else>NÃO!</div>
        </div>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  computed: {
    candidato() {
      const jsonData = require("../mockdata.json");
      return jsonData.candidatos[this.$route.params.id - 1];
    },
  },
};
</script>
