<template>
  <form class="form" @submit.prevent="onSubmit">
    <div class="inputContainer">
      <label for="input" class="label">Пожалуйста, введите число от 1 до 100</label>
      <input
          id="input"
          class="input"
          v-model="value"
          placeholder="Число"
          type="number"
          min="1"
          max="100"
      />
    </div>
    <button type="submit">Проверить</button>
  </form>
</template>

<script>
export default {
  props: ['id', 'label'],
  data: () => ({
    value: ''
  }),
  methods: {
    onSubmit() {
      this.$emit('submit', this.value);
    }
  }
}
</script>

<style scoped>
.form {
  padding: 15px;
  border: 1px solid #24282F;
  width: 450px;
}

.form > button {
  margin-top: 10px;
  width: 100%;
  height: 100%;
  padding: 0.5rem 1rem;
  font-weight: 500;
  font-size: 16px;
  color: #f3f3f3;
  background: #FF9A00;
  transition: all .1s ease-in-out;
  border: 1px solid transparent;
  cursor: pointer;
  outline: none;
}

.form > button:hover {
  background: transparent;
  border: 1px solid #FF9A00;
  color: #24282F;
}

.inputContainer {
  display: flex;
  flex-direction: column;
  text-align: center;
}

.label {
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  margin-bottom: 3px;
}

.input {
  height: 60px;
  padding: 10px 21px;
  background: #171D21;
  border: 1px solid #171D21;
  box-sizing: border-box;
  border-radius: 5px;
  font-style: normal;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  color: #FFFFFF;
  outline: none;
}

.input::-webkit-outer-spin-button,
.input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

.input[type=number] {
  -moz-appearance: textfield;
}

@media (max-width: 600px) {
  .form {
    width: 280px;
  }
}
</style>
