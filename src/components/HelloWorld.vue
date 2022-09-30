<template>
  <div class="greetings">
    <div class="pippo"></div>
    <h1 class="red">{{ msg }}</h1>
    <h1 class="BigNumRD">{{ num }}</h1>
    <h1 class="needed">{{ need }}</h1>
    <h1 class="oggetto">{{ obj }}</h1>
    <button @click="$emit('qualcosa', 'ciao')">BOTTONE</button>
    <button @click="$emit('input', value + 1)">TEST V-MODEL</button>
  </div>
</template>
<script>
export default {
  props: {
    msg: String,
    num: Number,
    need: {
      type: String,
      required: true,
    },
    value: {
      type: Number,
    },
    obj: {
      type: Object,
      required: false,
      default: function () {
        return { message: "la programmazione è difficile" };
      },
    },
  },
};
</script>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

.needed {
  color: yellow;
}

.red {
  color: red;
}

.BigNumRD {
  color: red;
  border: 2px solid black;
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
    display: block;
    text-align: left;
  }
}
</style>
