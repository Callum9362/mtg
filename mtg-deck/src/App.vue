<template>
  <div id="app">
  </div>
</template>

<script>

const mtg = require('mtgsdk')

mtg.card.find(3)
.then(result => {
  console.log(result.card.name)
})

export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
</style>
