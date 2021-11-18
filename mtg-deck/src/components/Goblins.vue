<template>
    <div id="Goblins" class="flex flex-col bg-white m-auto p-auto">
        <h1 class="flex py-5 lg:px-20 md:px-10 px-5 lg:mx-40 md:mx-20 mx-5 font-bold text-4xl text-gray-800">Legendary Goblins</h1>
            <div class="flex overflow-x-scroll pb-10 hide-scroll-bar">
                <div class="flex flex-nowrap lg:ml-40 md:ml-20 ml-10">
                    <div class="inline-block px-3">
                        <div v-for="goblin in goblins" :key="goblin.name" class="w-64 h-64 max-w-xs overflow-hidden rounded-lg shadow-md bg-white hover:shadow-xl transition-shadow duration-300 ease-in-out">
                            <img v-bind:src="goblin.imageUrl" alt="img" title="img" class=" h-70 w-40 object-cover" id="whoobe-7jr8o">
                            <h4 class="mt-8 border-b-2" id="whoobe-5f06f">{{ goblin.name }}</h4>
                        </div>	
                    </div>
                </div>
            </div>
    </div>
</template>

<script>
const mtg = require('mtgsdk')

export default {
    name: 'Goblins',
    data: function() {
        return {
            goblins: mtg.card.where({ supertypes: 'legendary', subtypes: 'goblin', page: 1, pageSize: 10 }).then(cards => { this.goblins = cards })
        }
    }
}
</script>

<style>
.hide-scroll-bar {
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.hide-scroll-bar::-webkit-scrollbar {
  display: none;
}
</style>