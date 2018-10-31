<template>
    <v-container v-bind:style="{ height: containerHeight }">
        <svg height="100%" width="100%" viewBox="0 0 50 50">
            <circle r="25" cx="25" cy="25" fill="#f00" />
        </svg>
  </v-container>
</template>

<script>
  export default {
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
