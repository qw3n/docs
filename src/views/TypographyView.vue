<template lang="pug">
  div(class="view" id="typography-view")
    div
      section-def
        dt(slot="title") {{ doc.title }}
        dd(slot="desc") {{ doc.desc }}
    section
      section-header Examples
      div(class="component-example")
        div(class="component-example__container")
          dl(class="headings")
            dt(class="primary") h1
            dd
              div(class="display-4 grey--text text--darken-1") Light 112sp
              strong display-4
              span font-weight 300
            dt(class="primary") h2
            dd
              div(class="display-3 grey--text text--darken-1") Regular 56sp
              strong display-3
              span font-weight 400
            dt(class="primary") h3
            dd
              div(class="display-2 grey--text text--darken-1") Regular 45sp
              strong display-2
              span font-weight 400
            dt(class="primary") h4
            dd
              div(class="display-1 grey--text text--darken-1") Regular 34sp
              strong display-1
              span font-weight 400
            dt(class="primary") h5
            dd
              div(class="headline grey--text text--darken-1") Regular 24sp
              strong headline
              span font-weight 400
            dt(class="primary") h6
            dd
              div(class="title grey--text text--darken-1") Regular 20sp
              strong title
              span font-weight 500
</template>

<script>
  export default {
    name: 'typography-view',

    data () {
      return {
        doc: {
          title: 'Typography',
          desc: 'The typography of an application is just as important as its functionality. Vuetify.js uses the Material Design spec Roboto Font. Each heading size also has a corresponding helper class to style other elements the same.'
        },
        lorem: 'Lorem ipsum dolor sit amet, brute iriure accusata ne mea. Eos suavitate referrentur ad, te duo agam libris qualisque, utroque quaestio accommodare no qui. Et percipit laboramus usu, no invidunt verterem nominati mel. Dolorem ancillae an mei, ut putant invenire splendide mel, ea nec propriae adipisci. Ignota salutandi accusamus in sed, et per malis fuisset, qui id ludus appareat.'
      }
    },

    mounted () {
      this.$emit('view', this.meta())
    },

    preFetch () {
      return this.methods.meta()
    },

    methods: {
      meta () {
        return {
          title: 'Typography | Vuetify.js',
          h1: 'Typography',
          description: 'Typography for the Vuetify Framework',
          keywords: 'vuetify, typography'
        }
      }
    }
  }
</script>

<style lang="stylus">
  #typography-view
    .component-example__container
      > div, dl
        width: 100%
        
      .headings
        dt, dd
          float: left
          
        dt
          width: 32px
          height: 32px
          border-radius: 50%
          text-align: center
          line-height: 32px
          color: #fff
          clear: both
        
        dd
          margin: 0 0 3rem 2rem
          
          > div
            margin-bottom: 16px
            
          strong
            margin-right: 16px
</style>