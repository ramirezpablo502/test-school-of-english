<template>
  <div>
    <NavbarComponent />
    <div class="container">
      <div class="shadow-content">
        <p class="title-section">Inicio de sesión</p>
        <div class="form">
          <v-text-field
            v-model="email"
            label="correo electrónico"
            required
          ></v-text-field>
          <v-text-field
            v-model="password"
            label="Contraseña"
            type="password"
            required
          ></v-text-field>
        </div>
        <v-btn @click="login" :disabled="!validateForm">Entrar</v-btn>
        <p class="link" @click="redirectSignup">
          ¿Aún no estas registrado? Registrate
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import NavbarComponent from "@/components/Navbar.vue";

export default {
  name: "LoginView",
  data() {
    return {
      email: "",
      password: "",
    };
  },
  methods: {
    redirectSignup: function () {
      this.$router.push("/signup");
    },
    login: function () {
      if (this.email === "test@gmail.com" && this.password == "123") {
        this.$router.push("/chat");
      } else {
        alert("Los datos capturados son incorrectos.");
      }
    },
  },
  computed: {
    validateForm: function () {
      return this.email !== "" && this.password !== "";
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
