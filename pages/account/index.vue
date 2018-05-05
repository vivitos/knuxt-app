<template>
    <div>
        <knavbar/>
        <div class="flex justify-center mt-4 text-grey-darker rounded">
            <div class="flex flex-col shadow-lg pt-4 pb-4 bg-white items-center w-1/4">
                <div class="relative flex mb-2">
                    <img src="/avatar.png" alt="Vivitos" width="120" height="120" class="rounded-full border border-solid border-grey-lighter">
                </div>
                <h2 class="leading-tight text-center text-black mb-4">Vivien Brunel</h2>
                <p class="mb-1">Poste: Défenseur</p>
                <p class="mb-1">Matchs joués: 200</p>
                <p class="mb-1">Victoires: 120</p>
                <p>Défaites: 80</p>
            </div>
        </div>
    </div>
</template>
<script>
import * as axios from 'axios';
import Knavbar from '~/components/Knavbar';

export default {
    components: {
        Knavbar
    }
}

</script>