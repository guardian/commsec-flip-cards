<template lang="pug">
  .card.column(
    v-on:click="flipCard"
    v-bind:class="{ 'flipped': isFlipped }"
  )
    .card-flip-icon
    .card__wrapper
      .card__front
        .image
          img(:src="card.image" width="352px", height="352px")
        header
          h2 {{ card.title }}
          p {{ card.intro }}

      .card__back
        header
          .image
            img(:src="card.image" width="88px", height="88px")
          h3 {{ card.title }}
          p Tips for this strategy

        .content(v-html="card.description")

</template>

<script>
export default {
  props: ['card'],

  data: function() {
    return {
      isFlipped: false,
    }
  },

  methods: {
    flipCard: function() {
      this.isFlipped = !this.isFlipped
    },
  },
}
</script>
