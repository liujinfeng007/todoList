<template>
  <ul class="todo-main">

    <transition-group name="animate__animated animate__bounce" appear
                      enter-active-class="animate__backInRight"
                      leave-active-class="animate__backOutDown"
    >
      <MyItem v-for="todoObj in todo" :key="todoObj.id" :mytodo="todoObj"></MyItem>
    </transition-group>


  </ul>
</template>

<script>
import "animate.css"
import MyItem from "@/components/MyItem";

export default {
  name: "MyList",
  components: {
    MyItem
  },
  props: ["todo"]

}
</script>

<style scoped>
/*main*/
.todo-main {
  margin-left: 0;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}

.todo-enter-active {
  animation: todo 0.5s linear;
}

.todo-leave-active {
  animation: todo 0.5s linear reverse;
}

@keyframes todo {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0px);
  }

}
</style>