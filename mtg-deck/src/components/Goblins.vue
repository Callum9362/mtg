<template>
    <div id="Goblins">
    <div v-for="goblin in goblins" :key="goblin.name" id="whoobe-swr0n" class="pt-4 bg-white w-full md:w-56 justify-center items-center shadow px-6 py-4 flex flex-col">
	<img v-bind:src="goblin.imageUrl" alt="img" title="img" class=" h-70 w-40 object-cover" id="whoobe-7jr8o">
	<h4 class="mt-8 border-b-2" id="whoobe-5f06f">{{ goblin.name }}</h4>
    </div>
    </div>
</template>

<script>
const mtg = require('mtgsdk')

export default {
    name: 'Goblins',
    data: function() {
        return {
            goblins: mtg.card.where({ supertypes: 'legendary', subtypes: 'goblin' }).then(cards => { this.goblins = cards })
        }
    }
}
</script>

<style>
</style>