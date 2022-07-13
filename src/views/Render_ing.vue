<template>
  <div>
    <h1>Rendering</h1>
    <input type="text" v-model="type"><br>
    <h1 v-if="changeType(type)==='A'">A</h1>
    <h1 v-else-if="type==='B'">B</h1>
    <h1 v-else>C</h1>
    <hr>
    <h1 v-show="changeType(type)==='A'">A</h1>
    <h1 v-show="type==='B'">B</h1>
    <h1 v-show="changeType(type) !=='A' && type !== 'B'">C</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      type: 'A'
    }
  },
  methods: {
    changeType(type) {
      return type.toUpperCase();
    }
  }
}
</script>

<style>

</style>