<template>
  <div id="app">
    <form>
      <div class="mb-3">
        <h1>Crea una Nueva Tarea</h1>
        <label class="me-3">Tarea</label>
        <input type="text" v-model="task" class="form-control w-50 d-inline" />
      </div>
      <button type="button" @click="showTask" class="btn btn-primary">
        Crear
      </button>
    </form>
    <div>
      <h2 class="mt-2">Listado de Tareas</h2>
      <ul v-if="show" class="list-group">
        <li v-for="(ind, i) of newTask" :key="+i" class="list-task">
          {{ i + ":" + ind }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      newTask: [],
      show: true,
      task: "",
    };
  },
  methods: {
    showTask() {
      if (this.task == false) {
        alert("Ingresar una tarea");
      } else {
        this.newTask.push(this.task);
        return (this.task = "");
      }
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
.list-task {
  align-self: flex-start;
  margin-left: 34vw;
}
</style>
