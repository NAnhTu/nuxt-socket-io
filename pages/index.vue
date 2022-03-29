<template>
  <div class="container index-container">

    <div>
      <messages style="height: 500px; overflow-y: scroll;"></messages>
     
    </div>
  </div>
</template>

<script>
import Messages from '@/components/Messages.vue'

export default {
  components: {
    Messages
  }
}
</script>

<style scoped>
.index-container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
