<template>
  <div class="pag 1">
    <div class="linea1"></div>
    <h1>mia pagina</h1>
    <p>mi chiamo {{ nome }} e ho {{ eta }} anni</p>
    <p>
      oggi è il giorno {{ giorno() }} del mese numero {{ mese() }} e dell'anno
      {{ anno() }}
    </p>
    <p>{{ i }}</p>
    <p>{{ maiusc(argomento) }}</p>
    <p>{{ minusc("CASONA") }}</p>
  </div>
</template>

<script>
export default {
  mounted() {
    setInterval(() => {
      this.i++;
    }, 1000);
  },
  data() {
    return {
      nome: "pinuzzo",
      date: "2022-09-26",
      eta: 240,
      i: 0,
      argomento: "casa",
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
