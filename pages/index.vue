<template>
  <div class="content">
    <knavbar/>
    <div class="p-4 flex flex-wrap" v-if="matchs">
      <div class="w-full sm:w-1/2 md:w-1/4" v-for="match in matchs" v-bind:key="match.matchId">
        <match v-bind:match="match" />
      </div>
    </div>
  </div>
</template>

<script>
import Match from '~/components/Match.vue'
import Knavbar from '~/components/Knavbar.vue'
import * as axios from 'axios'
import conf from '~/api.config.js'

export default {
  components: {
    Knavbar,
    Match
  },
  asyncData ({ params, error }) {
    return axios.get(`${conf.conf.apiUrl}/matchs`)
      .then((res) => {
        return {
          matchs: res.data
        }
      })
      .catch((e) => {
        error({ statusCode: 404, message: 'Billet non trouvé' })
      })
  }
}
</script>

<style>

</style>
