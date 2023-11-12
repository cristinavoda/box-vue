<template>
  <div>
    <p>{{ nombreCompleto }}</p>
    <div class="boxes">
      <p class="positive">income: <br> {{ income }}</p>
      <p class="negative">expenses: <br>{{ expenses }}</p>
    </div>
    <p v-for="amount in sentTotal" :key="amount">{{ amount }}</p>
    <div id="balance-text" v-show="balance">
      <p class="positive-balance" :class="{ 'negative-balance' : (balance < 0)}">total disponible: {{ balance }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Box",
  props: ["sentTotal"],
  data() {
    return {
      nombre: "Irene",
      apellido: "Valle"
    };
  },
  computed: {

    nombreCompleto() {
      return this.nombre + this.apellido
    }
  },
};
</script>

<style>
.boxes {
  display: flex;
  justify-content: space-between;
  background-color: white;
  padding-left: 3rem;
  padding-right: 3rem;
  margin-top: 2rem;
  border-radius: 0.5rem;
  box-shadow: 0.2rem 0.1rem 0.2rem black;
}
.positive {
  color: rgb(80, 159, 1);
  font-weight: bold;
}
.positive-balance {
    box-shadow: 0.2rem 0.1rem 0.2rem rgb(80, 159, 1);
}
.negative-balance {
    box-shadow: 0.2rem 0.1rem 0.2rem rgb(171, 5, 5);
}
.negative {
  color: rgb(171, 5, 5);
  font-weight: bold;
}
#balance-text {
  color: black;
  font-weight: bold;
  display: flex;
  justify-content: end;
}
#balance-text p{
    background-color: rgb(255, 255, 255);
    padding: 1rem 3rem 1rem 3rem;
    border-radius: 0.5rem;
}
</style>
