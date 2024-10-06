<script setup>
import { ref } from 'vue';

const text = ref('Click to edit');
const isEditing = ref(false);

const edit = () => {
  isEditing.value = true;
};

const save = () => {
  isEditing.value = false;
};
</script>

<template>
  <div class="greetings">
    <input v-if="isEditing" type="text" v-model="text" @keyup.enter="save" @blur="save"/>

    <label v-else @dblclick="edit">{{ text }}</label>
  </div>
</template>

<style scoped>
label, input {
  font-size: 30px;
}

h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
