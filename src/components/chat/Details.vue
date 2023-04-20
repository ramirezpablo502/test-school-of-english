<template>
  <div class="container-chat-details">
    <p>Ultima conexión: 16 Abril 2023 5:00pm</p>
  </div>
</template>

<script>
export default {
  name: "ChatDetailsView",
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.container-chat-details {
  padding: 10px;

  & > p {
    color: gray;
    font-size: 14px;
    margin-bottom: 0;
  }
}
</style>
