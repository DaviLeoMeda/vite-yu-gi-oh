<script>
import SingleCard from "./SingleCard.vue"
import { store } from "../store"


export default {
    name: "CardsFolder",
    components: {
        SingleCard
    },
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <div class="container py-5">
        <div class="row">
            <SingleCard v-for="(ele, index) in store.arrayCards" :key="index" :CardContent="ele" />
        </div>
    </div>
</template>

<style lang="scss" scoped></style>