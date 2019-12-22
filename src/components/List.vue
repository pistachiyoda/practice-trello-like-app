<template>
  <div>
    <draggable
      class="list-wrapper"
      :list="TODO"
      group="people"
      @change="log"
      draggable=".item"
    >
      <h3 class="list-title rounded-top " slot="header">{{ listName }}</h3>
      <div v-for="task in TODO" :key="task.id" class="each-background item">
        <b-card>
          {{ task.name }}
        </b-card>
      </div>
      <div class="list-title rounded-bottom">
        <b-form-input
          placeholder="＋タスクを追加する"
          slot="footer"
          type="text"
          v-model="inputTodoTask"
          @keydown.enter="addTask"
        >
        </b-form-input>
      </div>
    </draggable>
  </div>
</template>

<script>
import draggable from "vuedraggable";

export default {
  name: "two-lists",

  display: "Two Lists",

  order: 1,

  components: {
    draggable
  },
  props: ["listName"],
  data() {
    return {
      currentId: 1,
      inputTodoTask: "",
      TODO: []
    };
  },

  methods: {
    addTask: function() {
      // eslint-disable-next-line
      console.log("keydown test");
      this.currentId++;
      this.TODO.push({
        id: this.currentId,
        name: this.inputTodoTask
      });
      this.inputTodoTask = "";
    },
    log: function(evt) {
      window.console.log(evt);
    }
  }
};
</script>

<style scoped>
.list-wrapper {
  width: 200px;
  height: calc(100vh - 50px - 8px - 30px - 8px);
  margin-right: 20px;
}

.list-title {
  background-color: rgba(255, 255, 255, 0.6);
  padding: 10px;
  margin: 0;
  font-family: "Kosugi Maru", sans-serif;
  font-size: 18px;
}

.each-background {
  background-color: rgba(255, 255, 255, 0.6);
  padding: 10px;
  margin: 0;
  font-family: "Kosugi Maru", sans-serif;
}
</style>
