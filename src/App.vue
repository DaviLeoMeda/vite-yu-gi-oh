<script >
import axios from 'axios';
import { store } from './store.js'
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import CharFilter from "./components/CharFilter.vue"


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,
    CharFilter
  },
  data() {
    return {
      store
    }
  },

  created() {
    this.APICall(),

      this.ApiArche()
  },
  methods: {
    APICall() {

      if (store.valueArche !== '') {
        axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=${store.valueArche}`)
          .then((res) => {
            // console.log(res.data.data)

            const APIRes = res.data.data

            this.store.arrayCards = APIRes
          })
      } else {
        axios.get(`https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=3`)
          .then((res) => {
            // console.log(res.data.data)

            const APIRes = res.data.data

            this.store.arrayCards = APIRes
          })
      }


    },
    ApiArche() {
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((res) => {

          const APIArchety = res.data

          this.store.arrayChar = APIArchety
        })
    }
  }
}
</script>

<template>
  <HeaderComp />
  <CharFilter />
  <MainComp @emiSele="APICall()" />
</template>

<style lang="scss">
@use './style/main.scss';
</style>
