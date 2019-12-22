<template>
  <b-container fluid>
    <div class="row-wrapper justify-content-start d-flex">
      <div v-for="(list, index) in lists" :key="index">
        <List :listName="list.name"></List>
      </div>
      <div>
        <b-form-input
          placeholder="＋リストを追加する"
          class="list-input"
          type="text"
          v-model="inputList"
          @keydown.enter="addList"
        >
        </b-form-input>
      </div>
    </div>
  </b-container>
</template>

<script>
import List from "./List.vue";

export default {
  components: {
    List
  },
  data() {
    return {
      inputList: "",
      lists: [],
      selectedTask: null
    };
  },
  methods: {
    addList: function() {
      this.lists.push({
        name: this.inputList
      });
      this.inputList = "";
    }
  }
};
</script>

<style scoped>
.list-input {
  width: 200px;
}

.row-wrapper {
  flex-wrap: nowrap;
  overflow: auto;
}
</style>
