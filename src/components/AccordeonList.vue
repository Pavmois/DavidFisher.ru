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
      <p v-html="question.answer"></p>
    </Collapse>
  </div>
</template>

<script setup>
import { reactive } from "vue";
import { Collapse } from "vue-collapsed";

const questions = reactive([
  {
    title: "Кто я?",
    answer:
      "Меня зовут Давид.<br/><br/> Родом я из прекрасного города Сочи, однако уже больше <span>10</span> лет проживаю в Питере.",
    isExpanded: false,
  },
  {
    title: "Сколько я занимаюсь стримами?",
    answer:
      "Впервые я запустил стрим в <span>2019</span> году, по игре Outward. На тот момент я ещё не сформировал концепцию своих стримов, поэтому была даже без образа",
    isExpanded: false,
  },
  {
    title: "Не жарко ли мне в костюмах?",
    answer:
      "Это мой 'любимый' вопрос на стримах.<br/><br/> Нет, мне вполне комфортно, все мои костюмы <span>максимально</span> продуманы. Исключения составляют ситуации когда стоит аномальная жара. Ну тогда и в трусах и майке жарко.<br/><br/> Однако меня это не останавливает, ведь гораздо важнее не личный комфорт, а <span>атмосфера</span> на стриме.",
    isExpanded: false,
  },
  {
    title: "Работаю ли я где-нибудь сейчас?",
    answer:
      "Нет, стримы - это и есть моя <span>основная работа</span>. Я стараюсь для моих подписчиков, а они отвечают мне благодарностью.",
    isExpanded: false,
  },
  {
    title: "Возможно ли заказать у меня рекламу?",
    answer:
      "Конечно, вся информация для связи есть на странице <span>'Контакты'</span>, однако сразу предупреждаю - я против ставок на спорт, казино и прочего скам-говна.",
    isExpanded: false,
  },
  {
    title: "Есть ли у  меня расписание?",
    answer:
      "Да, я стримлю всегда кроме <span>вторника</span> и <span>пятницы</span>.<br/><br/> В эти дни у меня выходной, как и любого нормалього рабочего человека. По пятницам у нас проводится особый формат стримов на <a href='https://boosty.to/davidfisher' class='boosty' target='_blank'>Boosty</a>",
    isExpanded: true,
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
  border-radius: 20px;
  background-color: rgba(0, 0, 0, 0.7);
  border-radius: 15px;
  box-shadow: 0 0 12px;
}
button {
  font-size: 1.5rem;
  width: 100%;
  height: 45px;
  border: 1px solid white;
  outline: none;
  border-radius: 20px;
  background-color: rgba(0, 0, 0, 0.85);
  color: white;
  &:hover {
    cursor: pointer;
  }
}
.collapse {
  width: 100%;
  margin: auto;
  text-align: left;
  transition: height 300ms cubic-bezier(0.3, 0, 0.6, 1);
  :deep(p) {
    color: white;
    padding: 10px 20px;
    font-size: 1.25rem;
    font-weight: 400;
    line-height: 1.5rem;
    span {
      font-weight: 700;
      color: red;
    }
    .boosty {
      text-decoration: none;
      color: #f15f2c;
    }
  }
}
@media screen and (max-width: 1200px) {
  button {
    font-size: 1rem;
  }
  .collapse {
    :deep(p) {
      font-size: 1rem;
    }
  }
}
</style>
