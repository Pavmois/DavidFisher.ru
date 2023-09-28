<template>
  <div
    class="question"
    v-for="(question, index) in questions"
    :key="question.title"
  >
    <button @click="() => handleAccordion(index)">
      {{ question.title }}
    </button>
    <Collapse :when="questions[index].isExpanded" class="collapse">
      <p>
        {{ question.answer }}
      </p>
    </Collapse>
  </div>
</template>

<script setup>
import { reactive } from "vue";
import { Collapse } from "vue-collapsed";

const questions = reactive([
  {
    title: "Кто я?",
    answer: "Давид",
    isExpanded: true, // Initial value
  },
  {
    title: "Сколько я занимаюсь стримами?",
    answer: "Довольно давно",
    isExpanded: false,
  },
  {
    title: "Не жарко ли мне в костюмах?",
    answer: "В самый раз!",
    isExpanded: false,
  },
]);

function handleAccordion(selectedIndex) {
  questions.forEach((_, index) => {
    questions[index].isExpanded =
      index === selectedIndex ? !questions[index].isExpanded : false;
  });
}
</script>

<style lang="scss" scoped>
.question {
  margin-bottom: 1rem;
}
button {
  font-size: 1.5rem;
  width: 90%;
}
.collapse {
  margin: auto;
  text-align: left;
  width: 90%;
  transition: height 200ms cubic-bezier(0.3, 0, 0.6, 1);
  p {
    background: aqua;
    font-size: 1.25rem;
  }
}
</style>
