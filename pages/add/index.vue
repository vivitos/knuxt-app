<template>
    <div class="content">
        <knavbar/>
        <div class="w-full sm:w-2/3 md:w-1/3 ml-auto mr-auto mt-4">
            <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4" v-on:submit.prevent="addMatch()">
                <div class="flex flex-wrap">
                    <div class="w-1/2 px-2">
                        <label class="block text-grey-darker text-sm font-bold mb-2" for="team1">
                            Equipe 1
                        </label>
                        <input v-model="teams[0].name" class="shadow appearance-none border rounded w-full py-2 px-3 text-grey-darker" id="team1" type="text" placeholder="Nom" required>
                    </div>
                    <div class="w-1/2 px-2">
                        <label class="block text-grey-darker text-sm font-bold mb-2" for="team2">
                            Equipe 2
                        </label>
                        <input v-model="teams[1].name" class="shadow appearance-none border rounded w-full py-2 px-3 text-grey-darker mb-3" id="team2" type="text" placeholder="Nom" required>
                    </div>
                    <div class="w-1/2 px-2 text-center">
                        <input v-model="teams[0].goals" class="shadow appearance-none border rounded w-1/2 py-2 px-3 text-grey-darker" id="goals1" type="number" placeholder="Buts" required>
                    </div>
                    <div class="w-1/2 px-2 text-center">
                        <input v-model="teams[1].goals" class="shadow appearance-none border rounded w-1/2 py-2 px-3 text-grey-darker mb-3" id="goals2" type="number" placeholder="Buts" required>
                    </div>
                </div>
                <div class="text-center">
                    <button class="bg-blue hover:bg-blue-dark text-white font-bold py-2 px-4 rounded" type="submit">
                        Ajouter un match
                    </button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
import * as axios from 'axios';
import Knavbar from '~/components/Knavbar';
import conf from '~/api.config.js'

export default {
    components: {
        Knavbar,
    },
    data () {
        return {
            teams: [{
                name: '',
                goals: ''
            },
            {
                name: '',
                goals: ''
            }]
        };
    },
    methods: {
        addMatch () {
            axios.put(`${conf.conf.apiUrl}/matchs`, { teams: this.teams })
                .then(() => {
                    this.$swal({
                        type: 'success',
                        title: 'Match ajouté'
                    })
                }, () => {
                    this.$swal({
                        type: 'error',
                        title: 'Un problème est survenu'
                    })
                });
        }
    }
}

</script>