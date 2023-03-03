import Cronometro from './Cronometro.vue';

<template>
  <Caixa>
    <div class="columns">
      <div class="column is-7">{{tarefa.descricao || 'Simple Task'}}</div>
      <div class="column">
        <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
      </div>
    </div>
  </Caixa>
</template>

<script lang="ts">
import ITarefa from "../interfaces/ITarefa";
import { defineComponent, PropType } from "vue";
import Cronometro from "./Cronometro.vue";
import Caixa from "./Caixa.vue";

export default defineComponent({
  name: "Tarefa",
  components: {
    Cronometro,
    Caixa
},
  props: {
    tarefa: {
        type: Object as PropType<ITarefa>,
        required: true
    }
  }
});
</script>
