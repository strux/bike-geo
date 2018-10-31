<template>
    <g :visibility="visibility" :id="model" fill="none" :stroke="color" stroke-width="4">
        <wheel v-bind:size="wheelSize" v-bind:x="rearWheelPosition.x" v-bind:y="rearWheelPosition.y"></wheel>
        <wheel v-bind:size="wheelSize" v-bind:x="frontWheelPosition.x" v-bind:y="frontWheelPosition.y"></wheel>
    </g>
</template>

<script>
  import Wheel from './Wheel'

  export default {
    components: {
        Wheel,
    },
    props: ['enabled', 'viewBoxWidth', 'viewBoxHeight', 'model', 'wheelSize', 'wheelBase', 'color'],
    data: () => ({
    }),
    computed: {
        wheelRadius() {
            return this.wheelSize/2
        },
        rearWheelPosition() {
            return { x: this.wheelRadius, y: this.viewBoxHeight - this.wheelRadius }
        },
        frontWheelPosition() {
            return { x: this.wheelRadius + this.wheelBase, y: this.viewBoxHeight - this.wheelRadius }
        },
        visibility() {
            return this.enabled ? 'visible' : 'hidden'
        },
    },
  }
</script>

<style>

</style>
