<template>
  <div id="app">
    <Form @submit="submitHandler"/>
    <div class="answer">
      Ответ: {{ answer }}
    </div>
  </div>
</template>

<script>
import Form from "@/components/Form";

export default {
  name: 'App',
  components: { Form },
  data: () => ({
    answer: 'Число не введено'
  }),
  methods: {
    submitHandler(value) {
      const checkMOD = mod => +value % mod === 0;
      let result = 'Число не делится без остатка ни на 3, ни на 6';
      if (checkMOD(3)) result = 'Молоко';
      if (checkMOD(6)) result = 'Кофе';
      if (checkMOD(3) && checkMOD(6)) result = 'Капучино';
      this.answer = result;
    }
  }
}
</script>

<style>
#app {
  font: 112.5%/1.625 -apple-system, 'BlinkMacSystemFont', 'Segoe UI', 'Roboto', 'Helvetica', 'Arial', sans-serif, 'Apple Color Emoji', 'Segoe UI Emoji', 'Segoe UI Symbol';
  font-style: normal;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  min-height: 100vh;
  background: #f3f3f3;
}

.answer {
  padding: 15px;
  border: 1px solid #24282F;
  border-top: none;
  width: 450px;
  text-align: center;
}

@media (max-width: 600px) {
  .answer {
    width: 280px;
  }
}
</style>
