<template>
  <div id="app">
  <codeCompiler></codeCompiler>
  </div>
</template>

<script>
import codeCompiler from '@/components/code_editor'
export default {
  name: "App",
  components: {
    codeCompiler
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
