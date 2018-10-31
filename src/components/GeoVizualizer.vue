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
            // TODO: temporarily using wheel size for total size
            return this.bikes.reduce((a, b) => a.wheelSize > b.wheelSize ? a.wheelSize : b.wheelSize)
        },
        viewBoxHeight: function() {
            // TODO: temporarily using wheel size for total size
            return this.bikes.reduce((a, b) => a.wheelSize > b.wheelSize ? a.wheelSize : b.wheelSize)
        },
        viewBoxDef: function() {
            return `0 0 ${this.viewBoxWidth} ${this.viewBoxHeight}`
        },
    },
  }
</script>

<style>

</style>
