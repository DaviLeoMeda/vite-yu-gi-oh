<script>
import CardsFolder from "./CardsFolder.vue"

export default {
    name: "MainComp",
    components: {
        CardsFolder
    }
}
</script>

<template>
    <main>
        <div class="bg-oranger d-flex flex-column justify-content-center">
            <CardsFolder />
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/partials/variables.scss' as *;

.bg-oranger {
    background-color: $bg-orange;
}
</style>