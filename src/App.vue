<script >
import axios from 'axios';
import { store } from './store.js'
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data() {
    return {
      store
    }
  },

  created() {
    this.APICall()
  },
  methods: {
    APICall() {
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=3')
        .then((res) => {
          // console.log(res.data.data)

          const APIRes = res.data.data

          this.store.arrayCards = APIRes
        })
    },
    ApiArche() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((res) => {

          const APIArchety = res.archetype_name

          this.store.arrayChar = APIArchety
        })
    }
  }
}
</script>

<template>
  <HeaderComp />
  <MainComp />
</template>

<style lang="scss">
@use './style/main.scss';
</style>
