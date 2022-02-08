<template>
  <div class="home">
    <v-text-field
      v-model="newTaskField"
      @click:append="addTask"
      @keyup.enter="addTask"
      class="pa-3"
      outlined
      label="Add Task"
      append-icon="mdi-plus"
      hide-details
      clearable
    ></v-text-field>
    <v-list class="pt-0" flat>
      <!-- <v-subheader>Hangout notifications</v-subheader> -->
      <div v-for="task in tasks" :key="task.id">
        <v-list-item
          @click="doneTask(task.id)"
          :class="{ 'blue lighten-5': task.done }"
        >
          <template v-slot:default>
            <v-list-item-action>
              <v-checkbox :input-value="task.done" color="primary"></v-checkbox>
            </v-list-item-action>

            <v-list-item-content>
              <v-list-item-title
                :class="{ 'text-decoration-line-through': task.done }"
              >
                {{ task.title }}
              </v-list-item-title>
            </v-list-item-content>
            <v-list-item-action>
              <v-btn @click.stop="deleteTask(task.id)" icon>
                <v-icon color="blue lighten-1">mdi-delete</v-icon>
              </v-btn>
            </v-list-item-action>
          </template>
        </v-list-item>
        <v-divider></v-divider>
      </div>
    </v-list>
  </div>
</template>

<script>
export default {
  name: 'Home',

  data() {
    return {
      newTaskField: '',
      tasks: [
        {
          id: 1,
          title: 'wake Up',
          done: false,
        },
        {
          id: 2,
          title: 'Task 2',
          done: false,
        },
        {
          id: 3,
          title: 'task 3',
          done: false,
        },
      ],
    };
  },
  methods: {
    doneTask(id) {
      let task = this.tasks.filter(task => task.id === id)[0];
      task.done = !task.done;
    },
    deleteTask(id) {
      this.tasks = this.tasks.filter(task => task.id !== id);
    },
    addTask() {
      let newTask = {
        id: Date.now(),
        title: this.newTaskField,
        done: false,
      };
      this.tasks.push(newTask);
      this.newTaskField = '';
    },
  },
};
</script>
