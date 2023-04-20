<template>
  <div class="container-content-chat">
    <div class="content-bubbles-messages">
      <div v-for="(item, i) in listMessages" :key="i">
        <div class="bubble-message">{{ item.text }}</div>
      </div>
    </div>
    <div>
      <input v-model="message" class="input-message" @keyup.enter="onEnter" />
      <v-btn :disabled="!validateForm" @click="sendMessage">Enviar</v-btn>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChatContentView",
  data() {
    return {
      message: "",
      listMessages: [
        {
          text: "Hola",
        },
      ],
    };
  },
  methods: {
    onEnter: function () {
      const obj = {
        text: this.message,
      };

      if (this.message) {
        this.listMessages.push(obj);
        this.message = "";
      }
    },
    sendMessage: function () {
      const obj = {
        text: this.message,
      };

      this.listMessages.push(obj);
      this.message = "";
    },
  },
  computed: {
    validateForm: function () {
      return this.message !== "";
    },
  },
};
</script>

<style lang="scss" scoped>
.container-content-chat {
  & > div:first-child {
    height: calc(100vh - 91px);
    overflow: scroll;
  }

  & > div:last-child {
    display: flex;
    align-items: center;
    height: 50px;
    padding: 5px 10px;
    background-color: #f2f2f2;
  }
}

.content-bubbles-messages {
  padding: 20px;
}

.input-message {
  box-shadow: 0px 10px 10px #00000020;
  width: calc(100% - 100px);
  margin-right: 15px;
  border-radius: 5px;
  height: 35px;
  background-color: #fff;
  padding: 5px 15px;
  font-family: "Roboto-Medium", sans-serif;
}

.bubble-message {
  background-color: #a8e4a0;
  padding: 5px 15px;
  width: fit-content;
  border-radius: 10px;
  margin-bottom: 15px;
}
</style>
