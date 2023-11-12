<!-- // vuein -->
<template>
    <form @submit.prevent class="todo-header">
      <h1 class="title">Список задач</h1>
      <input :value="task" @input="valueTask" class="todo-inputtype" type="text" placeholder="Укажите задачу"/>
      <!-- подключили событие к кнопке (@click="createTask")-->
      <button @click="createTask" class="btn">+</button>       
    </form> 
</template>
<script>
export default {
    name: 'todoHeader',
    props() {                   // функция позволяет указывать свои данные

    },
}
</script>

<style scope>
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
    
</style>