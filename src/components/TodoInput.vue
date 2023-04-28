<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" />
    <button v-on:click="addTodo">+</button>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      newTodoItem: "",
    };
  },
  methods: {
    addTodo: function () {
      console.log(this.newTodoItem);
      //저장하는 로직
      localStorage.setItem(this.newTodoItem, this.newTodoItem);
      this.newTodoItem = ""; //비워주기(초기화)
    },
    clearInput: function () {
      this.newTodoItem = ""; //비워주기(초기화)
    },
  },
};
</script>

<style scoped>
input:focus {
  outline: none;
}
.inputBox {
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, #62eac6, #32cee6);
  display: block;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}
</style>
