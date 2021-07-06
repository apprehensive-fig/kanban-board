<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col form-inline">
        <b-form-input v-model="newTask" placeholder="Enter Task" @keyup.enter="add"></b-form-input>
      </div>
    </div>
    <div class="row mt-3">
      <div class="col-md-3">
        <div class="p-2 alert alert-primary">
          <h3>To Do</h3>
          <draggable class="list-group" :list="arrToDo" group="tasks">
            <div class="list-group-items" v-for="element in arrToDo" :key="element.name">
              {{element.name}}
            </div>
          </draggable>
        </div>
      </div>

       <div class="col-md-3">
        <div class="p-2 alert alert-warning">
          <h3>Backlog</h3>
          <draggable class="list-group" :list="arrBacklog" group="tasks">
            <div class="list-group-items" v-for="element in arrBacklog" :key="element.name">
              {{element.name}}
            </div>
          </draggable>
        </div>
      </div>

       <div class="col-md-3">
        <div class="p-2 alert alert-secondary">
          <h3>In Progress</h3>
          <draggable class="list-group" :list="arrInProgress" group="tasks">
            <div class="list-group-items" v-for="element in arrInProgress" :key="element.name">
              {{element.name}}
            </div>
          </draggable>
        </div>
      </div>

       <div class="col-md-3">
        <div class="p-2 alert alert-success">
          <h3>Done</h3>
          <draggable class="list-group" :list="arrDone" group="tasks">
            <div class="list-group-items" v-for="element in arrDone" :key="element.name">
              {{element.name}}
            </div>
          </draggable>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable";

export default {
  name: 'App',
  components: {
    draggable
  },
  data() {
    return {
      newTask: "",
      arrToDo: [
        {name: "Code"},
        {name: "Test"},
        {name: "Style"},
        {name: "Push"}
      ],
      arrBacklog: [],
      arrInProgress: [],
      arrDone: []
    }
  },
  methods: {
    add() {
      if(this.newTask) {
        this.arrBacklog.push({name: this.newTask});
        this.newTask= "";
      }
    }
  }
}
</script>
