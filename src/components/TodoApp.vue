<template>
  <div class="todo-list">
    <h2 class="text-center">
      Todo App
    </h2>

    <div class="d-flex mt-4">
      <input v-model="task" type="text" class="form-control" placeholder="Enter todos...">
      <button class="btn btn-outline-success" @click="submitTask">Add</button>
    </div>

    <table class="table table-bordered mt-5 text-center">
      <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Task</th>
        <th scope="col">Status</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(task, index) in tasks" :key="index">
        <th scope="row">{{ index + 1 }}</th>
        <td>{{ task.name }}</td>
        <td>{{ task.isDone ? 'Done' : 'In progress' }}
          <div class="btn-group" style="margin-left: 10px">
            <button class="btn btn-sm btn-outline-danger" @click="deleteTask(index)">
              Delete
            </button>
          </div>
        </td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'TodoApp',
  props: {
    msg: String
  },

  data() {
    return {
      task: '',
      tasks: [
        {
          name: 'Make my life better',
          isDone: false
        }
      ],
    }
  },

  methods: {
    submitTask() {
      if (this.task.length === 0) {
        return;
      }

      this.tasks.push({
        name: this.task,
        isDone: false
      });

      this.task = '';
    },

    deleteTask(index) {
      this.tasks.splice(index, 1);
    }
  }
}
</script>

<style scoped>

</style>
