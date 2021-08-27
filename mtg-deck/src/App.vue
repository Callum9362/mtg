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

mtg.card.where({ supertypes: 'legendary', subtypes: 'goblin'})
.then(cards => {

  cards.forEach(card => {
    console.log(card.name)
  });
  
})

export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
</style>
