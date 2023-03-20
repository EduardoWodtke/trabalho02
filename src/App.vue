<script setup>
import { ref, computed } from 'vue'

const contador = ref(0)
const contador2 = ref(0)

const soma = computed(() => {return contador.value + contador2.value})

</script>

<template>
  <div class="info">
    <button @click="$event => contador++">+</button>
    <button @click="$event => contador--">-</button>
    <p>Valor do contador é: {{ contador }}</p>
    <hr/>
    <div id="vermelho" v-if="contador > 10">
      O numero maior que 10
    </div>
    <div id="azul" v-else-if="contador < 10">
      O numero menor que 10
    </div>
    <div v-else>
      O numero é 10
    </div>
    <hr />
    <div v-if="contador % 2 === 0">
      É par
    </div>
    <div v-else>
      É ímpar
    </div>
    
    <hr/>

    <button @click="$event => contador2++">+</button>
    <button @click="$event => contador2--">-</button>
    <p>Valor do contador é: {{ contador2 }}</p>
    <hr/>
    <div id="vermelho" v-if="contador2 > 10">
      O numero maior que 10
    </div>
    <div id="azul" v-else-if="contador2 < 10">
      O numero menor que 10
    </div>
    <div v-else>
      O numero é 10
    </div>
    <hr />
    <div v-if="contador2 % 2 === 0">
      É par
    </div>
    <div v-else>
      É ímpar
    </div>
    <hr/>
    <div>
      soma:{{ soma }}
    </div>
    <div v-if="soma % 2 === 0">
      é par
    </div>
    <div v-else>
      É ímpar
    </div>
  </div>
</template>

<style scoped>
button {
  font-weight: bold;
  cursor: pointer;
}
#vermelho {
  color: red;
}
#azul {
  color: green;
}
.info {
  background-color: rgba(35, 12, 22, 1);
  padding: 20px 30px;
  color: rgb(183, 210, 219);
  border-radius: 10px;
}
h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}
</style>