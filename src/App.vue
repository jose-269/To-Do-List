<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <div class="tarea">
      <h1>Crear nueva Tarea</h1>
      <div class="tasks">
        <label class="task">Tarea</label>
        <input v-model="tareas" type="text" class="labelInput" />
        <button @click="ingresarTareas()">Crear</button>
      </div>
      <h2>Lista</h2>
      <ol class="lista">
        <li v-for="tareas in arrTareas" :key="tareas">
          {{ tareas }}
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      arrTareas: [],
      tareas: "",
    };
  },
  methods: {
    ingresarTareas() {
      if (this.tareas === "") return;
      this.arrTareas.push(this.tareas);
      this.tareas = "";
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.lista {
  display: flex;
  display: inline-block;
  flex-direction: column;
  padding: 0;
}
.labelInput {
  margin: 0 1rem;
  font-size: 1rem;
}
.task {
  font-weight: 700;
  font-size: 1.5rem;
}
.tasks {
  display: flex;
  justify-content: center;
}
</style>
