<template>
  <HomePage></HomePage>
</template>

<script>
import HomePage from "@/components/HomePage";

export default {
  name: 'App',
  components: {
    HomePage
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

:root {
  --primery-color: #1a1d3c;
  --secondary-color: white;
  --secondary-color-rgb: 255, 255, 255;
  --tertiary-color: #744483;
}

*{
  margin : 0;
  padding : 0;
  background-color: var(--primery-color);
}

html, body {
  display: flex;
  flex-direction: column;
  width: 100%;
  position: relative;
  justify-content: center;
  align-items: center;
  font-family: Myfont, sans-serif;
}

</style>
