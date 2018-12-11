<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
html, body {
  height: 100%;
  width: 100%;
  margin: 0px;
  padding: 0px;
}

#app {
  height: 100%;
  width: 100%;
}

/* ul {
  margin: 0px;
  padding: 6px 6px 52px 0px;
  border-radius: 8px;
  height: 20x
}

li {
  padding: 6px 12px;
  list-style: none;
} */
</style>
