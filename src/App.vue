<template>
  <div id="app">
    <Insight/>
  </div>
</template>

<script>
import Insight from '@/views/Insight'

export default {
  name: 'App',
  components: { Insight } 
}
</script>

<style>
/*
=============== 
Variables
===============
*/

:root {
  /* darkest grey - used for headings */
  --clr-grey-1: #f7f7f7;
  --clr-grey-2: #5B5B5B;
  --clr-grey-3: #727272;
  --clr-grey-4: #C5C5C5;
  --clr-grey-5: #d2d2d2;
  --clr-grey-6: #707070C4;
  --clr-grey-7: #4D4F5C;
  --clr-grey-8: #8b8b8b;
  --clr-grey-9: hsl(212, 33%, 89%);
  --clr-grey-10: hsl(210, 36%, 96%);
  --clr-white: #fff;
  --clr-red-dark: hsl(360, 67%, 44%);
  --clr-red-light: #FF5656;
  --clr-green-dark: #37B04C;
  --clr-green-light: rgb(214,237,218);
  --clr-black: #000000DE;
  --clr-cream: #FFE7BD;

  --transition: all 0.3s linear;
  --spacing: 0.1rem;
  --radius: 2px;
  --light-shadow: 0px 2px 6px #0000000A;
  --dark-shadow: 0px 3px 6px #00000029;
  --max-width: 1280px;
  --fixed-width: 620px;
  --border: 0.5px solid #D2D2D2;
}

*,
::after,
::before {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

h1 {
  font-size: 40px;
}

h3 {
  font-size: 20px;
}

button {
  background: none;
  border: none;
  cursor: pointer;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: var(--clr-grey-1)
}

.content-container {
  width: 100%;
  min-height: calc(100vh - 64px);
  padding: 32px 32px 32px 24px;
  display: grid;
  place-items: center;
  overflow-y: auto;
}

.page-content {
  width: 100%;
  max-width: 1152px;
  height: 100%;
  position: relative;
}

.card {
  background-color: var(--clr-white);
  border: var(--border);
  border-radius: var(--radius);
  padding: .65rem 1rem;
  box-shadow: var(--light-shadow);
}

.card-head {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 24px;
}
</style>
