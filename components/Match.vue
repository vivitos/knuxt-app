<template>
    <div class="p-4 m-4 shadow-md text-center text-grey-darker">
        <div class="mb-1">
            <span v-bind:class="{ 'text-blue': match.teams[0].goals > match.teams[1].goals, 'text-grey': match.teams[0].goals === match.teams[1].goals, 'text-black': match.teams[0].goals < match.teams[1].goals }">{{ match.teams[0].name }}</span>
            <span>&#32;-&#32;</span>
            <span v-bind:class="{ 'text-blue': match.teams[1].goals > match.teams[0].goals, 'text-grey': match.teams[0].goals === match.teams[1].goals, 'text-black': match.teams[1].goals < match.teams[0].goals }">{{ match.teams[1].name }}</span>
        </div>
        <p class="font-bold">
            SCORE : {{ match.teams[0].goals }} - {{ match.teams[1].goals }}
        </p>
    </div>
</template>

<script>
export default {
    props: ['match']
}
</script>

<style>

</style>