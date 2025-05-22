<script setup>
import { reactive } from "vue";
import  Cabecalho  from "./components/Cabecalho.vue";
import  Formulario  from "./components/Formulario.vue";
import  Resultado  from "./components/Resultado.vue";

  const estado = reactive({
      val1: 0,
      val2: 0,
      res: '',
  })

  const calc = () => {
    const { res, val1, val2} = estado;
    switch (res) {
      case '+':
        return val1 + val2;
        break;
        case '-':
        return val1 - val2;
        break;
        case '*':
        return val1 * val2;
        break;
        case '/':
        return val2 !== 0 ? val1 / val2 : "Erro divisão por zero";
        break;
        case '%':
        return val2 !== 0 ? val1 % val2: "Erro: resto da divisão por zero!";
        break;
        default:
      return "Escolha uma operação";
    }
  }
</script>

<template>
  <div class="container">
    <Cabecalho/>
    <Formulario
    :val1="(evento) => (estado.val1 = Number(evento.target.value))"
      :val2="(evento) => (estado.val2 = Number(evento.target.value))"
      :res="(evento) => (estado.res = evento.target.value)"/>
    <Resultado
    :calc="calc()"
      :resultado="`${estado.val1} ${estado.res} ${
        estado.val2
      } = ${calc()}`"/>
  </div>
</template>

<style scoped>

</style>
