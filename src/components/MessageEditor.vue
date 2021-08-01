<template>
  <div>
    <textarea ref="textarea" @change="onChange($event)"> </textarea>
    <div>
      <button @click="onSendClick()">send</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "",
    };
  },
  components: {},
  methods: {
    onChange(event) {
      this.message = event.target.value;
    },
    onSendClick() {
      this.$emit("send", this.message);
      this.message = "";
      this.$refs.textarea.value = "";
    },
  },
};
</script>

<style>
</style>