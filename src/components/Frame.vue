<template>
    <g>
        <line :x1="rearAxle.x" :y1="rearAxle.y" :x2="bb.x" :y2="bb.y"></line>
        <line :x1="headTubeTop.x" :y1="headTubeTop.y" :x2="bb.x" :y2="bb.y"></line>
    </g>
</template>

<script>
  export default {
    props: ['rearAxle', 'bbDrop', 'chainStay', 'stack', 'reach'],
    data: () => ({
    }),
    computed: {
        bb: function() {
            return { x: (this.rearAxle.x + this.chainStay), y: (this.rearAxle.y + this.bbDrop) }
        },
        headTubeTop: function() {
            return { x: (this.bb.x + this.reach), y: (this.bb.y - this.stack) }
        },
    },
  }
</script>

<style>

</style>
