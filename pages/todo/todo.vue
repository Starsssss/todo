<template>
  <div class="todos">
    <h1>待办事项1212</h1>

    <!-- 显示待办事项列表 -->
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo }}
        <button @click="removeTodo(index)">删除</button>
      </li>
    </ul>

    <!-- 添加待办事项表单 -->
    <form @submit.prevent="addTodo">
      <input type="text" v-model="newTodo" placeholder="输入待办事项" />
      <button type="submit" @click="addTodo">添加</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      newTodo: ''
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== '') {
        this.todos.push(this.newTodo);
		console.log(this.todos);
        this.newTodo = '';
		  
      }else{
		  console.log(this.todos);
	  }
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    }
  }
};
</script>

<style scoped>
h1 {
  text-align: center;
  margin-top: 20px;
}

.todos {
  max-width: 400px;
  margin: 0 auto;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 10px;
  padding: 10px;
  background-color: #f5f5f5;
  border-radius: 5px;
}

button {
  padding: 5px 10px;
  background-color: #ff5a5f;
  color: white;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}

form {
  display: flex;
  margin-top: 20px;
}

input[type="text"] {
  flex-grow: 1;
  padding: 5px;
  border: 1px solid #ccc;
  border-radius: 3px;
}

button[type="submit"] {
  padding: 5px 10px;
  background-color: #4caf50;
  color: white;
  border: none;
  border-radius: 3px;
  cursor: pointer;
  margin-left: 10px;
}
</style>