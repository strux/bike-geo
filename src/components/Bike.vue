<template>
    <g :visibility="visibility" :id="model" fill="none" :stroke="color" stroke-width="4">
        <wheel v-bind:size="wheelSize" v-bind:x="rearAxle.x" v-bind:y="rearAxle.y"></wheel>
        <wheel v-bind:size="wheelSize" v-bind:x="frontAxle.x" v-bind:y="frontAxle.y"></wheel>
        <frame v-bind:frontAxle="frontAxle" v-bind:rearAxle="rearAxle" v-bind:bbDrop="bbDropCalc" v-bind:chainStay="chainStay" v-bind:stack="stack" v-bind:reach="reach"></frame>
    </g>
</template>

<script>
  import Wheel from './Wheel'
  import Frame from './Frame'

  export default {
    components: {
        Wheel,
        Frame,
    },
    props: ['enabled', 'viewBoxWidth', 'viewBoxHeight', 'model', 'wheelSize', 'wheelBase', 'color', 'bbHeight', 'bbDrop', 'chainStay', 'stack', 'reach'],
    data: () => ({
        tireHeight: 59,
        tireHeightPlus: 78,
    }),
    computed: {
        visibility() {
            return this.enabled ? 'visible' : 'hidden'
        },
        wheelRadius() {
            return this.wheelSize/2
        },
        rearAxle() {
            return { x: this.wheelRadius, y: this.viewBoxHeight - this.wheelRadius }
        },
        frontAxle() {
            return { x: this.wheelRadius + this.wheelBase, y: this.viewBoxHeight - this.wheelRadius }
        },
        bbDropCalc() {
            return (this.viewBoxHeight - this.bbHeight + this.tireHeight) - (this.rearAxle.y)
        },
    },
  }
</script>

<style>

</style>
