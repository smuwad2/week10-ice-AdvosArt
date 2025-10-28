<script>
import TaskTracker from './subcomponents/TaskTracker.vue';

    export default {
        data() {
            return {
                desc: '',
                deadline: '',
                taskList: []
            }
        },
        methods: {
            add() {
                this.taskList.push( { 'desc': this.desc, 'deadline': this.deadline } )
                this.desc = ''
                this.deadline = ''
            },
            // TODO: Add a new method, to delete a task completed
            deleteTask(taskId) {
                    this.taskList.splice(taskId, 1);
            }
        },
        components: {
            TaskTracker
        }
    }

</script>

<template>
    <div class="mb-3">
        <label for="desc" class="form-label">Task</label>
        <input type="text" class="form-control" id="desc" v-model='desc' placeholder="task">
    </div>
    <div class="mb-3">
        <label for="deadline" class="form-label">Deadline</label>
        <input type="date" class="form-control" id="deadline" v-model='deadline' placeholder="deadline">
    </div>

    <button type="button" @click="add" class="btn btn-primary">Add New Task</button>
    <hr>

    <!-- TODO: Modify following code -->
    <TaskTracker
    v-for="task in taskList"
    v-bind:task="task"
    v-bind:idx="taskList.indexOf(task)"
    v-on:delete="deleteTask"
    >
    </TaskTracker>

</template>

<style scoped>
   
</style>
