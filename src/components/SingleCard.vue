<script>

export default {
    name: "SingleCard",
    props: ['CardContent']

}
</script>

<template>
    <div class="card col-3">
        <img :src="CardContent.card_images[0].image_url" class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{ CardContent.name }}</h5>
            <p class="card-text">{{ CardContent.archetype }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped></style>