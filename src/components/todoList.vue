<template>
    <div class="todo-main">
      <ul class="todo-list">
        <!-- В каждую Li создать кнопку к примеру a class="todo-delite" иконку в виде корзинки-->
        <li v-bind:key="t" v-for="t in listTask" class="todo-item">{{ t.task }}
          <a :id="t.id" @click.prevent @click="delitTask" href="#" class="todo-list__delit">удалить</a></li> 
      </ul>
    </div>
</template>
<script>
export default {
    
}
</script>
<style lang="">
    
</style>
