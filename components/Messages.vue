<template>
  <div>
    <div>
      <h2>Component-defined method:</h2>
      <p>
        This example uses <code>"getMessage()"</code> defined in the component
        and consumes <code>chatMessages</code> that were sent directly to Vuex
      </p>
      <label>If you can see text appear in the box, it worked!</label>
      <button @click="getMessage()">Get Message</button>
      <b-form-textarea
        v-model="messageRxd"
        placeholder="[messageRxd] Waiting for you to click the 'Get Message' button..."
        rows="3"
        max-rows="6"
      ></b-form-textarea>
      <b-form-textarea
        v-model="chatMessages"
        placeholder="[chatMessages] Formatted messages will appear here"
        rows="3"
        max-rows="6"
      ></b-form-textarea>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  data() {
    return {
      messageRxd: '',
      testMsg: { id: 'xyz' }
    }
  },
  computed: mapState(['chatMessages']),
  mounted() {
    this.socket = this.$nuxtSocket({
      channel: '/index',
      reconnection: false
    })
  },
  methods: {
    getMessage() {
      return new Promise((resolve) => {
        this.socket.emit('getMessage', { id: 'abc123' }, (resp) => {
          this.messageRxd = resp
          resolve()
        })
      })
    }
  }
}
</script>

<style scoped>
.message-rxd-textbox {
  width: 500px;
  height: 500px;
}
</style>
