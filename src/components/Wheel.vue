<template>
    <circle :r="radius" :cx="x" :cy="y" />
</template>

<script>
  export default {
    props: ['size', 'x', 'y'],
    data: () => ({
    }),
    computed: {
        radius: function() {
            return this.size / 2
        },
    },
  }
</script>

<style>

</style>
