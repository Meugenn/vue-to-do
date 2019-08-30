<template>
  <div class="wrapper">
    <h1 class="title">Eugene, do</h1>
    <main>
      <Task></task>
    </main>
  </div>
</template>

<script>
import Task from './components/Task';

export default {
  components: {
    "Task": Task
  }
}
</script>

<style lang="scss">
body{
  font-family: BlinkMacSystemFont,"Segoe UI",Roboto,Oxygen,Ubuntu,Cantarell,"Fira Sans","Droid Sans","Helvetica Neue",Helvetica,Arial,sans-serif
}

.wrapper{
  text-align: center;
}

.title{
  margin-top: 10px
}


</style>
