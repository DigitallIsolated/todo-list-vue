<template>
  <div id="app">
    <TodoApp/>
  </div>
</template>

<script>
import TodoApp from "@/components/TodoApp";

export default {
  name: 'App',
  components: {
    TodoApp
  }
}
</script>

<style>
  #app {
    padding: 90px 0 137px 0;
    max-width: 841px;
    margin: 0 auto;
  }
</style>
