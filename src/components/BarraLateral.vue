<template>
    <header>
        <h1>
            <img class="logo__superior" src="../assets/logo.png" alt="Logotipo">
        </h1>
        <button class="button" @click="alterarTema">
          <img class="logo__modo__escuro" src="../assets/modo-escuro.png" alt="icon modo-escuro">
          <!-- {{ textoBotao }} -->
        </button>
    </header>
</template>

<script lang="ts">

import { defineComponent } from 'vue';


export default defineComponent ({
    name: 'BarraLateral',
    emits: ['aoTemaAlterado'],
    data () {
      return {
        modoEscuroAtivo: false
      }
    },
    computed: {
      // textoBotao () {
      //   if(this.modoEscuroAtivo) {
      //     return '- Dark mode' //Turn off 
      //   }
      //   return '- Dark mode' //Turn on 
      // }
    },
    methods: {
      alterarTema () {
        this.modoEscuroAtivo = !this.modoEscuroAtivo
        this.$emit('aoTemaAlterado', this.modoEscuroAtivo)
      }
    }
})

</script>

<style scoped>
header {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
  text-align: center;
}

.logo__superior {
  width: 130px;
  height: 130px;
}

.button {
  margin-top: 30px;
  padding: 24px;
  border-radius: 10px;
  background-color: azure;
}

.button:hover {
  background-color: rgb(212, 220, 220);
  transition: 0.3s all;
}

.logo__modo__escuro {
  width: 40px;
}

@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>