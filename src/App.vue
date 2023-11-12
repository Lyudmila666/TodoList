<template>
  <div class="todolist">
    <form @submit.prevent class="todo-header">
      <h1 class="title">Список задач</h1>
      <input :value="task" @input="valueTask" class="todo-inputtype" type="text" placeholder="Укажите задачу"/>
    <!-- подключили событие к кнопке (@click="createTask") -->
      <button @click="createTask" class="btn">+</button>       
    </form>   
    <!-- видеть все записи на фронтэнде -->
    <div class="todo-main">
      <ul class="todo-list">
         <!-- В каждую Li создать кнопку к примеру a class="todo-delite" иконку в виде корзинки -->
        <li v-bind:key="t" v-for="t in listTask" class="todo-item">{{ t.task }}
          <a :id="t.id" @click.prevent @click="delitTask" href="#" class="todo-list__delit">
            <img width="18" src="./assets/free-icon-bin-5976474.png" alt="корзина"/>удалить</a></li> 
      </ul>
    </div>
  </div>
  
</template>

<script>
// import todoList from "./components/todoList.vue";
// import todoHeader from "./components/todoHeader.vue";
export default {
  data() {
    return {
      listTask: [
        {id: 1, task: "Выполнить дизайн"},          // чтобы получить все эти данные, нужно в теге li прописать цикл v-for (v-bind:key="t" v-for="t in listTask")
        {id: 2, task: "Сделать верстку сайта"},
        {id: 3, task: "Загрузить репозиторий"},
      ],
      task: " ",         // здесь устанавливается задача
      data: 0,
    };
  },
  methods: {
    valueTask(event) {
      this.task = event.target.value;
    },
    createTask() {
      const newTask = {
        id: Date.now(),
        task: this.task,
      };
      console.log(newTask);
      this.listTask.push(newTask);
      this.task = " ";
    },
    delitTask(event) {                   // перебирая id в listTask
      console.log(event.target);
    },
  },
};


</script>

<style scope>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(#21b8ba, #0ad077);
  background-repeat: no-repeat;
}
#app {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 100px;
  margin-top: 75px;
}
.title {
  margin-top: 20px;
  font-size: 32px;
  text-align: center;
  margin-bottom: 30px;
}
.todo-inputtype {
  padding: 10px 20px;
  border: 1px solid #ccc;
  border-radius: 20px;
  width: 300px;
}
.btn {
  font-size: 40px;
  padding: 0px 15px;
  border-radius: 50%;
  background-color: red;
}
.todo-main {
  margin-top: 30px;
}
.todo-list {
  list-style: none;
  margin: 0;
  padding: 0;
  font-size: 0;
}
.todo-item {
  font-size: 20px;
  color: #000;
  padding: 5px 10px;
  background-color: #fff;
  margin-top: 5px;
  margin-bottom: 5px;
  border-radius: 10px;
}
</style>


