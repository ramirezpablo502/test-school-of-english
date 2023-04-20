<template>
  <div class="container-contact-list">
    <h1>Lista de contactos</h1>
    <div v-for="(item, i) in contacts" :key="i" class="items-chat">
      <div class="icon">
        {{ item.name.charAt(0) }}
      </div>
      <div class="texts">
        <p>{{ item.name }}</p>
        <p>{{ item.dummyMessage }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChatContactListView",
  data() {
    return {
      contacts: [
        {
          id: 1,
          name: "Carlos",
          dummyMessage: "Hola",
        },
        {
          id: 2,
          name: "Juan",
          dummyMessage: "Hey",
        },
        {
          id: 3,
          name: "Alejandra",
          dummyMessage: "Hello",
        },
        {
          id: 4,
          name: "Carolina",
          dummyMessage: "Como has estado?",
        },
        {
          id: 5,
          name: "Sofia",
          dummyMessage: "¿Estas ahi?",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.container-contact-list {
  padding: 10px;

  & > h1 {
    font-family: "Roboto-Bold", sans-serif;
    font-size: 18px;
    text-align: center;
    padding-bottom: 10px;
    border-bottom: 1px solid #00000050;
  }
}

.items-chat {
  margin-bottom: 5px;
  display: flex;
  align-items: center;
  box-shadow: 0px 10px 10px #00000050;
  padding: 10px;
  border-radius: 5px;
}

.icon {
  background-color: pink;
  width: 35px;
  height: 35px;
  border-radius: 100%;
  padding: 5px;
  font-size: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.texts {
  padding: 5px 10px;

  & > p:first-child {
    color: #212121;
    font-size: 16px;
    font-family: "Roboto-Bold", sans-serif;
    margin-bottom: 0;
  }

  & > p:last-child {
    color: #21212150;
    font-size: 16px;
    font-family: "Roboto-Bold", sans-serif;
    margin-bottom: 0;
  }
}
</style>
