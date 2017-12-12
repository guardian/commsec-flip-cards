<template lang="pug">
main
  article
    section.container
      .cards.row(v-bind:class="{ 'loaded': isLoaded }")
        transition-group(name="scale-fade")
          card(
            v-for="(card, index) in cards",
            :key="index",
            v-bind:card="card"
          )

      .row
        .cta.column
          h4 What's next?
          p
            | For more information on opening a share trading account and what CommSec offers, go to
            a(href="https://www.commsec.com.au/why-join-commsec/choosing-an-online-broker.html")  https://www.commsec.com.au/why-join-commsec/choosing-an-online-broker.html
          p
            a.button(href="https://www.commsec.com.au/why-join-commsec/choosing-an-online-broker.html") Find out more

        .disclaimer.column
          p Disclaimer: As this information has been prepared without taking into account your objectives, financial situation or needs you should, before acting on this information, consider its appropriateness for your objectives, financial situation or needs and, if necessary, seek appropriate professional advice.

</template>

<script>
// vue components
import Card from './components/card.vue'
//card data
import cards from './card-data.js'
//region date

export default {
  components: {
    Card,
  },

  data() {
    return {
      cards,
      isLoaded: false,
    }
  },

  methods: {
  },

  computed: {
  },

  mounted: function () {
    setTimeout( () => {
      this.isLoaded = true
    }, 800)
  }
}
</script>
