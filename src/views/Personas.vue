<!--  Aqui todo el codigo HTL-->
<template>
  <div>
    <h1>Lista de personas</h1>

    Nombre: <input type="text" v-model="nombre">
    <br>
    Hola como estas {{ nombre }}

    <hr>

    N1: <input type="text" v-model="n1"> <br>
    N2: <input type="text" v-model="n2"> <br>

<!--    <button v-on:click="multiplicacion()"> Multiplicar</button>-->
    <button @click="multiplicacion"> Multiplicar</button>

    <br>
    La suma es: {{ sumar }} <br>
    La multipliacaion es: {{ multiplicar }}

    <hr>

    <h3>Lista de personal</h3>

    <input type="text" v-model="txtBuscar"> <br>
    <br>

    <table border="1" width="100%">
      <tr>
        <th>Nombre</th>
        <th>Edad</th>
        <th>Carnet</th>
      </tr>

      <tr v-for="(row, index) in personasBuscadas" :key="index">
        <td>{{ row.nombre }}</td>
        <td>{{ row.edad }}</td>
        <td>
          <strong v-if="row.carnet_conducir">SI</strong>
          <strong v-else>No</strong>
        </td>
      </tr>

    </table>

  </div>
</template>

<!--Aqui va todo el codigo java scritp o vuejs-->
<script>
export default {
  name: "Personas",
  data: () => ({
    //declarios de variables locales
    nombre: "",
    n1: 2,
    n2: 0,
    multiplicar: 0,
    txtBuscar: "",

    persona: [
      {
        "nombre": "Pepito Conejo",
        "edad": 25,
        "carnet_conducir": true
      },
      {
        "nombre": "Ana Barberá",
        "edad": 90,
        "carnet_conducir": false
      },
      {
        "nombre": "Lidia Marce",
        "edad": 25,
        "carnet_conducir": true
      },
      {
        "nombre": "Jose Luis Contreras",
        "edad": 25,
        "carnet_conducir": false
      },
      {
        "nombre": "Soyla Rincon",
        "edad": 17,
        "carnet_conducir": false
      },
      {
        "nombre": "Armando Iglesias Morales",
        "edad": 17,
        "carnet_conducir": false
      },
      {
        "nombre": "Carla Mamani",
        "edad": 27,
        "carnet_conducir": false
      },
      {
        "nombre": "Dorcar Mamani",
        "edad": 17,
        "carnet_conducir": false
      }
    ]

  }),
  computed: {
    //cambiar el estado o el valor de la variables en tiempo de ejecucios, operaciones de variables
    sumar() {
      return parseInt(this.n1) + parseInt(this.n2);
    },
    personasBuscadas(){
      return this.persona.filter(item => {
        return item.nombre.includes(this.txtBuscar);
      })
    }
  },
  created() {
    //se ejecuta antes de dibujar el DOM de la pagina
  },
  mounted() {
    //se ejecuda despues de dibujar el DOM de la pagina
  },
  methods: {
    //declarar todos los metodos o funciones del compoente
    multiplicacion(){
      this.multiplicar = parseInt(this.n1) *  parseInt(this.n2);
    }
  }
}
</script>

<!--codigo de estilos css para la vista o componente-->
<style scoped>

</style>