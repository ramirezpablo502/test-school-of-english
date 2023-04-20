<template>
  <div class="navbar">
    <p>School of English</p>
  </div>
</template>

<script>
export default {
  name: "NavbarComponent",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.navbar {
  background-color: #212121;
  color: #ffffff;
  padding: 10px 20px;
  height: 50px;

  display: flex;
  align-items: center;

  & > p {
    margin-bottom: 0;
  }
}
</style>
