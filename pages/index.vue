<template>
<!--  <Tutorial />-->
  <div>
    <div>{{response}}</div>
    <img :src="response.details.ext_1.url" width="800">
    <div v-for="n in response.details.ext_4" :key="n.slag" >
      <img :src="n.ext_4.url" width="400">
      <div>{{ n.ext_5 }}</div>
      <div>{{ n.ext_6 }}</div>
    </div>
  </div>
</template>

<script lang="js">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  async asyncData ({ $axios }) {
    try {
      const response = await $axios.$get(process.env.BASE_URL + '/rcms-api/5/service/3')
      return { response }
    }catch (e) {
      console.log(e.message)
    }
  }
})
</script>
