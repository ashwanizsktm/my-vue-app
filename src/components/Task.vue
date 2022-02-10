<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" class="task" :class="task.reminder ? 'reminder' : 'not-reminder'">
        <h3>
            {{ task.text }}
            <i @click="$emit('delete-task',task.id)" class="fas fa-times-circle"></i>
        </h3>
        <p>{{ task.day }}</p>
    </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },


};
</script>

<style scope>
.fas {
  color: red;
  font-size: 28px;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.task.reminder {
  border-left: 5px solid green;
}
.task.not-reminder{
    border-left: 5px solid red;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
