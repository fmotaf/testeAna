<template>
  <div>
    <!-- <h1>{{mockdataVue.candidatos}}</h1> -->
    <!-- <h1>Continent: {{ typeof mockdataVue }}</h1> -->
    <p>Path: {{ this.$route.query.id }}</p>
  </div>
</template>

<script>
export default {
  async asyncData({ params, redirect }) {
    const mountains = await fetch('https://localhost:3000/mockdata').then((res) => res.json())
    console.log("sadasd")
    // const filteredMountain = mountains.find(
    //   (el) =>
    //     el.continent.toLowerCase() === params.continent &&
    //     el.slug === params.mountain
    // )
    // if (filteredMountain) {
    //   return {
    //     continent: filteredMountain.continent,
    //     mountain: filteredMountain.title
    //   }
    // } else {
    //   console.log("sadasd")
    //   redirect('/')
    // }
  }
}
</script>
