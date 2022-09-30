<template>
  <div class="pag 1">
    <button @click="bottonio = !bottonio">
      questo bottone farà un operazione
    </button>
    <p v-if="bottonio">pulito</p>
    <template v-else>
      <pippo msg="Ciao" :num="154" need="necessariamente"></pippo>
      <pippo @qualcosa="foo" need=""></pippo>
      <pippo @input="foo" v-model="text" need=""></pippo>
      <pluto @input="ciao" v-model="pera"></pluto>
      <div class="linea1"></div>
      <h1>mia pagina</h1>
      <p>mi chiamo {{ nome }} e ho {{ eta }} anni</p>
      <p>{{ text }}</p>
      <p>
        oggi è il giorno {{ giorno() }} del mese numero {{ mese() }} e dell'anno
        {{ anno() }}
      </p>
      {{ pera }}
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
    </template>
  </div>
</template>

<script>
import pippo from "@/components/HelloWorld.vue";
import pluto from "./components/nuovoTest.vue";
export default {
  components: {
    pippo,
    pluto,
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
      oggetto: {
        foo: 1,
        bar: 2,
      },
      array: [3, 4],
      text: 0,
      pera: 10,
      bottonio: true,
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
    ciao() {
      window.alert("ciao a tutti");
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
