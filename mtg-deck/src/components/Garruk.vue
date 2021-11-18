<template>
    <div id="whoobe-swr0n" class="pt-4 bg-white w-full md:w-56 justify-center items-center shadow px-6 py-4 flex flex-col">
	<img v-bind:src="imageURL" alt="img" title="img" class=" h-70 w-40 object-cover">
	<h4 class="mt-8 border-b-2">{{ cardName }}</h4>
</div>
</template>

<script>
const mtg = require('mtgsdk')

export default {
    name: 'Card',
    data: function() {
        return {
            cardName: mtg.card.where({name: 'Garruk Wildspeaker'}).then(result => { this.cardName = result.card.name }), // Garruk
            imageURL: mtg.card.where({name: 'Garruk Wildspeaker'}).then(result => { this.imageURL = result.card.imageUrl })
        }
    }
}
</script>

<style>
</style>