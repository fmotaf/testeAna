<template>
  <div>
    <!-- <h1>{{this.$route.params}}</h1> -->
    <h2>{{ this.$route.params.id }}</h2>
       <ul>
    <li v-for="name in names">
      {{ name }}
    </li>
    </ul>
  </div>
</template>

<script>
import mockdata from  '../mockdata.json'

export default {
  computed: {
    names() {
      return mockdata.candidatos[this.$route.params.id - 1]
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
