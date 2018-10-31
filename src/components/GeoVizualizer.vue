<template>
    <v-container v-bind:style="{ height: containerHeight }">
        <svg height="100%" width="100%" viewBox="0 0 50 50">
            <wheel v-for="bike in bikes" :key="bike.model" v-bind:size="bike.wheelSize"></wheel>
        </svg>
  </v-container>
</template>

<script>
  import Wheel from './Wheel'
  export default {
    props: ['bikes'],
    components: {
        Wheel,
    },
    data: () => ({
        containerHeight: '200px',
    }),
    beforeMount: function() {
        this.containerHeight = window.innerHeight + 'px';
    }
  }
</script>

<style>

</style>
