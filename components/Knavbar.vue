<template>
    <nav class="flex justify-between flex-wrap bg-blue p-6">
        <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
            <div class="text-sm lg:flex-grow text-center text-lg font-bold">
                <router-link :to="{name: 'index'}" class="block mt-4 lg:inline-block lg:mt-0 text-teal-lighter hover:text-white mr-4">
                    Matchs
                </router-link>
                <router-link :to="{name: 'add'}" class="block mt-4 lg:inline-block lg:mt-0 text-teal-lighter hover:text-white mr-4">
                    Ajouter
                </router-link>
                <router-link :to="{name: 'account'}" class="block mt-4 lg:inline-block lg:mt-0 text-teal-lighter hover:text-white">
                    Mon compte
                </router-link>
            </div>
        </div>
    </nav>
</template>

<style>

</style>