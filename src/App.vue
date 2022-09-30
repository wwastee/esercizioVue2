<template>
  <div class="pag 1">
    <pippo msg="Ciao" :num="154" need="necessariamente"></pippo>
    <pippo @qualcosa="foo" need=""></pippo>
    <pippo @input="foo" v-model="text" need=""></pippo>
    <div class="linea1"></div>
    <h1>mia pagina</h1>
    <p>mi chiamo {{ nome }} e ho {{ eta }} anni</p>
    <p>{{ text }}</p>
    <p>
      oggi è il giorno {{ giorno() }} del mese numero {{ mese() }} e dell'anno
      {{ anno() }}
    </p>
    <p>{{ i }}</p>
    <p>{{ maiusc(argomento) }}</p>
    <p>{{ minusc("CASONA") }}</p>
    <p>{{ n }}</p>
    <p>{{ moltiplicaz }}</p>
    <p>{{ addizione }}</p>
    <p>
      {{ oggetto.foo }} <br />
      {{ oggetto.bar }}
    </p>
    <p>{{ array[0] }} {{ array[1] }}</p>
  </div>
</template>

<script>
import pippo from "@/components/HelloWorld.vue";
export default {
  components: {
    pippo,
  },

  computed: {
    moltiplicaz: function () {
      return this.i * 2;
    },
    addizione: function () {
      return this.i + 2;
    },
  },
  mounted() {
    console.log(this);
    setInterval(() => {
      this.i++;
    }, 1000);
    setTimeout(() => {
      console.log((this.n = "3 secondi"));
    }, 3000);
  },
  data() {
    return {
      nome: "pinuzzo",
      date: "2022-09-26",
      eta: 240,
      i: 0,
      argomento: "casa",
      n: "",
      z: 1,
      ciao: "califragilistichespiralidoso",
      oggetto: {
        foo: 1,
        bar: 2,
      },
      array: [3, 4],
      text: 0,
    };
  },
  methods: {
    giorno() {
      return new Date(this.date).getUTCDate();
    },
    mese() {
      return new Date(this.date).getMonth();
    },
    anno() {
      return new Date(this.date).getFullYear();
    },
    maiusc(qualsiasi) {
      return qualsiasi.toUpperCase();
    },
    minusc(qualz2) {
      return qualz2.toLowerCase();
    },
    foo(arg) {
      console.log(arg);
    },
  },
};
</script>

<style>
body {
  background: grey !important;
  justify-content: center;
  align-items: center;
  display: flex;
}

h1 {
  color: orange;
  font-size: 100px;
  font-weight: 700;
}

p {
  color: white;
  font-size: 30px;
}

.linea1 {
  height: 5px;
  width: 500px;
  position: absolute;
  background: black;
}
</style>
