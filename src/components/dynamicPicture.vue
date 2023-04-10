<script>
export default {
    props: {
        customMargin: Number, //marge personnalisée à passer directement
        imageWidth: Number, //largeur de l'image (utilisé pour les calculs)
        pictureData: Object,
    },
    computed: {
        pictureStyles() {
            return {
                margin: `${this.customMargin}px`,
                '--picFlexBasis': `calc(${this.imageWidth}/260*200px)`,
                '--picFlexBasisMd': `calc(${this.imageWidth}/260*170px)`,
                '--picFlexBasisSm': `calc(${this.imageWidth}/260*110px)`,
                '--picFlexGrow': `calc(${this.imageWidth}/260*100)`,
            }
        }
    }
}
</script>

<template>
    <div role="img" class="picture_class max-h-72 overflow-hidden rounded-lg" :style="pictureStyles">
        <div class="picture_container">
            <div class="picture_wrapper">
                <img class="object-cover" :src="pictureData.largeImageURL" :alt="pictureData.user">
            </div>
        </div>
    </div>
</template>

<style scoped>
.picture_class {
    flex-basis: var(--picFlexBasis);
    flex-grow: var(--picFlexGrow);
}

@media (max-width:600px) {
    .picture_class {
        flex-basis: var(--picFlexBasisSm);
    }
}

@media (max-width:1023px) {
    .picture_class {
        flex-basis: var(--picFlexBasisMd);
    }
}
</style>