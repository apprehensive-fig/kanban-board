<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col form-inline">
        <b-form-input v-model="newTask">
    </div>
  </div>
</template>

<script>
import draggable "vuedraggable";


export default {
  name: 'App',
  components: {
    draggable
  },
  data() {
    return {
      newTask: "",
      arrBacklog: [
        {name: "Code Sign Up Page"}
        {name: "Test Dashboard"}
        {name: "Style Registration"}
        {name: "Help with Designs"}
      ],
      arrInProgress: [],
      arrTested: [],
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

<style>

</style>
