<template>
    <circle :r="radius" cx="25" cy="25" fill="#f00" />
</template>

<script>
  export default {
    props: ['size'],
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
