<template>   
  <div id="root">
    <Card />
    <Goblins/>
  </div>
</template>

<script>

import Card from './components/Card'
import Goblins from './components/Goblins'

export default {
  name: 'App',
  components: {
    Card,
    Goblins
  }
}
</script>

<style>
</style>
