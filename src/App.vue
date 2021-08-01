<template>
  <div id="app">
    <message-feed :messages="messages"></message-feed>
    <message-editor @send="onSend($event)"></message-editor>
  </div>
</template>

<script>
import MessageEditor from "./components/MessageEditor";
import MessageFeed from "./components/MessageFeed";
export default {
  name: "App",
  data() {
    return {
      messages: [],
    };
  },
  components: {
    MessageEditor,
    MessageFeed,
  },
  methods: {
    onSend(event) {
      this.messages = [...this.messages, event];
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
