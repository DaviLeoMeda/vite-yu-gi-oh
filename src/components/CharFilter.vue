<script>
import { store } from "../store"

export default {
    name: "CharFilter",
    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <select class="p-3" name="CharactersFilter" id="selection-arche" v-model="store.valueArche" @change="$emit('emiSele')">
        <option :value="elem.archetype_name" v-for="(elem, index) in store.arrayChar" :key="index">{{ elem.archetype_name }}
        </option>
    </select>
</template>

<style lang="scss" scoped></style>