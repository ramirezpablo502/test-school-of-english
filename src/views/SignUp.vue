<template>
  <div>
    <NavbarComponent />
    <div class="container">
      <div class="shadow-content">
        <p class="title-section">Registro de usuario</p>
        <div class="form">
          <v-text-field label="Nombre" required></v-text-field>
          <v-text-field label="Apellido" required></v-text-field>
          <v-text-field label="Teléfono" required></v-text-field>
          <v-text-field label="Correo electrónico" required></v-text-field>
          <v-text-field label="Usuario" required></v-text-field>
          <v-text-field
            label="Contraseña"
            type="password"
            required
          ></v-text-field>
        </div>
        <v-btn>Registrarse</v-btn>
        <p class="link" @click="redirectLogin">
          ¿Ya tienes cuenta? Incia sesión
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import NavbarComponent from "@/components/Navbar.vue";

export default {
  name: "SignUpView",
  data() {
    return {};
  },
  methods: {
    redirectLogin: function () {
      this.$router.push("/");
    },
  },
  components: {
    NavbarComponent,
  },
};
</script>

<style lang="scss" scoped>
.container {
  height: calc(100vh - 50px);
  display: flex;
  align-items: center;
  justify-content: center;

  @media (max-width: 600px) {
    height: 100%;
    padding: 10px;
  }
}

.shadow-content {
  text-align: center;
  background-color: #ffffff;
  box-shadow: 5px 10px 10px #00000030;
  width: 500px;
  padding: 20px;
  border-radius: 10px;

  @media (max-width: 600px) {
    width: 100%;
  }
}

.title-section {
  font-family: "Roboto-Bold", sans-serif;
  font-size: 2em;

  @media (max-width: 600px) {
    font-size: 18px;
  }
}

.form {
  margin-bottom: 1em;
}

.link {
  color: blue;
  font-size: 12px;
  margin-top: 1.5em;

  &:hover {
    cursor: pointer;
    text-decoration: underline;
  }
}
</style>
