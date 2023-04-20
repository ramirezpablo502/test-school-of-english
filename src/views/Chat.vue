<template>
  <div class="container">
    <div class="contact-list">
      <ContactList />
    </div>
    <div class="content-chat">
      <div class="content-details">
        <Details />
      </div>
      <div class="content-messages">
        <Content />
      </div>
    </div>
  </div>
</template>

<script>
import ContactList from "@/components/chat/ContactList.vue";
import Details from "@/components/chat/Details.vue";
import Content from "@/components/chat/Content.vue";

export default {
  name: "ChatView",
  data() {
    return {};
  },
  components: {
    ContactList,
    Details,
    Content,
  },
};
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  align-items: center;
  height: 100vh;
}

.contact-list {
  width: 250px;
  height: 100%;
  border-right: 1px solid #00000050;
}

.content-chat {
  width: calc(100% - 250px);
  height: 100%;
}

.content-details {
  border-bottom: 1px solid #00000050;
}
</style>
