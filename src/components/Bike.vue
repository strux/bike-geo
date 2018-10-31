<template>
    <g :visibility="visibility" :id="model" fill="none" :stroke="color" stroke-width="2">
        <wheel v-bind:size="wheelSize" v-bind:x="frontWheelPosition.x" v-bind:y="frontWheelPosition.y"></wheel>
    </g>
</template>

<script>
  import Wheel from './Wheel'

  export default {
    components: {
        Wheel,
    },
    props: ['enabled', 'viewBoxWidth', 'viewBoxHeight', 'model', 'wheelSize', 'color'],
    data: () => ({
    }),
    computed: {
        frontWheelPosition() {
            return { x: this.viewBoxWidth/2, y: this.viewBoxHeight/2 }
        },
        visibility() {
            return this.enabled ? 'visible' : 'hidden'
        },
    },
  }
</script>

<style>

</style>
