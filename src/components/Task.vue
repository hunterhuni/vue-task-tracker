<template>
  <div class="taskContainer" @dblclick="$emit('toggle-completed', task.id)">
    <i
      :class="[
        task.completed ? 'fa-regular fa-circle-check' : '',
        'fa-regular fa-circle',
      ]"
    ></i>
    <i class=""></i>
    <div :class="[task.completed ? 'completed' : '', 'task']">
      <h3>
        {{ task.text }}
        <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
      </h3>
      <p>{{ task.day }}</p>
    </div>
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
.taskContainer {
  display: flex;
  align-items: center;
  justify-self: center;
  cursor: pointer;
}

.fa-regular {
  font-size: 30px;
  margin-right: 5px;
}

.fa-circle-check {
  color: green;
}

.fas {
  color: red;
}

.task {
  width: 100%;
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  border-left: 5px solid black;
}

.task.completed {
  border-left: 5px solid green;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
