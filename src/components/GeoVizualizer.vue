<template>
    <v-container v-bind:style="{ height: containerHeight }">
        <svg height="100%" width="100%" :viewBox="viewBoxDef">
            <bike v-for="bike in bikes" :key="bike.model" v-bind="bike" v-bind:viewBoxWidth="viewBoxWidth" v-bind:viewBoxHeight="viewBoxHeight"  ></bike>
        </svg>
  </v-container>
</template>

<script>
  import Bike from './Bike'

  export default {
    props: ['bikes'],
    components: {
        Bike,
    },
    data: () => ({
        containerHeight: '0px',
    }),
    beforeMount: function() {
        this.containerHeight = window.innerHeight + 'px';
    },
    computed: {

        viewBoxWidth: function() {
            return this.bikes.reduce(function (a, b) {
                 const totalLength = (b.wheelSize + b.wheelBase)
                 return a > totalLength ? a: totalLength
            }, 0)
        },
        viewBoxHeight: function() {
            return this.bikes.reduce(function (a, b) {
                 const totalHeight = ((b.wheelSize / 2) + b.stack)
                 return a > totalHeight ? a: totalHeight
            }, 0)
        },
        viewBoxDef: function() {
            return `0 0 ${this.viewBoxWidth} ${this.viewBoxHeight}`
        },
    },
  }
</script>

<style>

</style>
