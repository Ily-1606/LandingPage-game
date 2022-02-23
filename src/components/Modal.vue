<template>
    <div class="modal fixed inset-0 bg-black/70 z-50" v-if="showModal">
      <div class="modal_content fixed left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2">
      <div class="relative">
            <div class="w-12 h-12 bg-close text-right absolute right-0 -top-12" @click="toogleModal"></div>
            <iframe width="720" class="aspect-video" :src="urlEmbed" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        </div>
      </div>
    </div>
</template>
<script>
export default {
    props: {
        showModal: {
            type: Boolean,
            default(){
                return false
            }
        },
        urlEmbed: {
            type: String,
            required: true
        }
    },
    emits: ["toogleModal"],
    methods: {
        toogleModal(){
            this.$emit('toogleModal')
        }
    },
}
</script>
<style scoped>
.bg-close{
    background-image: url('../assets/images/close.png');
    background-repeat: no-repeat;
}
</style>