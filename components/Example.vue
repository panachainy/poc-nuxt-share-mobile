<!-- Please remove this file from your project -->
<template>
  <div>
    <p>{{ response }}</p>
    <div>
      <button @click="share">Share นะจ๊ะ</button>
    </div>
    <div>
      <button @click="copyClipboard">copy clipboard นะจ๊ะ</button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return { response: 'default response' }
  },
  methods: {
    share() {
      if (navigator.share) {
        navigator
          .share({
            title: 'title this is google Demo',
            text: 'text this is google demo',
            url: 'https://www.google.co.th',
          })
          .then(() => {
            console.log('Thanks for sharing!')
          })
          .catch(console.error)
      } else {
        // fallback
        console.log('fallback')
      }
    },
    copyClipboard() {
      navigator.clipboard.writeText('https://www.google.co.th')
    },
  },
})
</script>
