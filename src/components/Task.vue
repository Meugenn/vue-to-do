<template>
    <div class="tasks">
        <draggable v-model='tasks'  >
            <div class="task" v-for="(task, index) in tasks" :key="task.id">
                {{task.text}} <span class="icon delete"  @click="deleteTask(index)"><!--<i class="fas fa-times-circle has-text-danger"></i>--></span>
            </div>
        </draggable>
        <input type="text" class="input task-button" placeholder="Input your task" v-model="newTaskText" @keyup.enter="appendTask()">
    </div>
</template>

<script>
import draggable from 'vuedraggable'

export default {
    data() {
        return {
            newTaskText: "",
            tasks: [

            ]
        }
    },

    methods: {
        appendTask(){
            if (this.newTaskText == '') return
            let newTask = {
                id: this.tasks.length + 1,
                text: this.newTaskText
            }
            this.tasks.push(newTask)
            this.newTaskText = ""
        },
        deleteTask(index){
            this.tasks.splice(index, 1)
        }
    },

    components: {
        draggable
    }

}
</script>

<style lang="scss">
@import 'bulma/bulma.sass';

.task-button{
    width: 20%;
}

.delete-task{
    position: absolute;
    right:1em
}

.task{
    position: relative;
    word-break: break-all;
    width:20%;
    border:#dbdbdb 1px solid;
    margin:5px auto;
    border-radius: 4px;
    padding:5px;
    padding-right:2em;
}
</style>
