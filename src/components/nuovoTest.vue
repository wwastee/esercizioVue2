<template>
  <div class="greetings">
    <div class="pluto"></div>
    <h1 class="titolo">{{ testolino }}</h1>
    <button @click="$emit('input', value * 2)">moltiplicare</button>
  </div>
</template>

<script>
export default {
  props: {
    testolino: String,
    value: null,
  },
};
</script>
>
