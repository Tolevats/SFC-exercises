<template>
  <div>
    <h2>Formulario de Bienvenida</h2>
    
    <!-- Formulario para capturar datos y mostrar un saludo -->
    <form @submit.prevent="mostrarSaludo">
      <label for="nombre">Nombre:</label>
      <input type="text" v-model="nombre" id="nombre" required />

      <label for="apellido">Apellido:</label>
      <input type="text" v-model="apellido" id="apellido" required />

      <label for="correo">Correo:</label>
      <input type="email" v-model="correo" id="correo" required />

      <label for="edad">Edad:</label>
      <input type="number" v-model="edad" id="edad" required />

      <button type="submit">Mostrar Saludo</button>
    </form>

    <!-- Mensaje para que el saludo se despliegue abajo del botón -->
 <!--    <div v-if="saludo">
      <p>{{ saludo }}</p>
    </div> -->

    <hr />

    <!-- Formulario para mostrar la etapa de vida según la edad -->
    <h2>Consulta de Etapa de Vida</h2>
    <form @submit.prevent="determinarEtapaVida">
      <label for="edadConsulta">Ingresa tu edad:</label>
      <input type="number" v-model="edadConsulta" id="edadConsulta" required />

      <button type="submit">Consultar Etapa</button>
    </form>

    <!-- Mensaje para que la etapa de vida según la edad se despliegue abajo del botón -->
<!--     <div v-if="etapaVida">
      <p>{{ etapaVida }}</p>
    </div> -->
  </div>
</template>

<script>
export default {
    name: 'FormsSFC',
    // props: {},
    data () {
      return {
        // Datos del primer formulario
        nombre: "",
        apellido: "",
        correo: "",
        edad: "",
        saludo: "",

      // Datos del segundo formulario
      edadConsulta: null,
      /* etapaVida: "" */
      };
    },
    // computed: {},
    methods: {
      mostrarSaludo() {
      // Generar el saludo con los datos ingresados y mostrar el saludo como alerta
      const saludo = `Hola ${this.nombre} ${this.apellido}, tu correo es: ${this.correo} y tienes ${this.edad} años. ¡Bienvenidx!`;
      alert(saludo);
    },
    determinarEtapaVida() {
      //Mostrar la etapa de vida basándose en la edad ingresada
      let etapaVida = "";
      
      if (this.edadConsulta >= 0 && this.edadConsulta <= 13) {
        etapaVida = "Niñez.";
      } else if (this.edadConsulta >= 14 && this.edadConsulta <= 17) {
        etapaVida = "Adolescencia.";
      } else if (this.edadConsulta >= 18 && this.edadConsulta <= 35) {
        etapaVida = "Adultos Jóvenes.";
      } else if (this.edadConsulta >= 36 && this.edadConsulta <= 64) {
        etapaVida = "Adulto.";
      } else if (this.edadConsulta >= 65) {
        etapaVida = "Tercera Edad.";
      } else {
        etapaVida = "Edad no válida.";
      }
      alert(`Etapa de vida: ${etapaVida}`); // Mostrar la etapa de vida como alerta
    }
  }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
};
</script>

<style scoped>
h2 {
  margin: 2rem 1rem;
}

hr {
  margin: 2rem 0;
  border: 1px solid #ccc;
}

form {
  display: flex;
  flex-direction: column;
  max-width: 400px;
  margin: 0 auto;
  padding: 1rem;
  background-color: #f8f8f8;
  border-radius: 8px;
  /* margin-bottom: 20px; */
}

label {
  font-weight: bold;
  margin: 0.5rem 0 0.2rem;
  font-weight: bold;
  /* margin-top: 10px; */
}

input {
  padding: 0.5rem;
  font-size: 1rem;
  margin-bottom: 1rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  /* margin-top: 5px; */
}

button {
  /* margin-top: 15px;*/
  padding: 0.7rem;
  font-size: 1rem;
  background-color: #007bff; /* #42b983*/
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  /* background-color: #358a69; */
  background-color: #0056b3;
}

@media (max-width: 600px) {
  form {
    padding: 0.5rem;
  }
  input,
  button {
    font-size: 0.9rem;
  }
}
</style>