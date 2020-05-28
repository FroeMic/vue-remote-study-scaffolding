<template>
  <div class="content-view">
      Content
      <p>
        {{testString}}
      </p>
  </div>
</template>

<script>
export default {
  name: 'ContentView',
  computed: {
    testString() {
      return this.$store.state.testString
    }
  }
}
</script>

<style>
  .content-view {
    height: 100vh;
    width: 100vw;
    overflow: scroll;
    background: white;
  }

</style>
