<script lang="ts">
import type { PropType } from 'vue';
import Tag from './Tag.vue';
export default {

  props: {
    ingredientes: {
      type: Array as PropType<string[]>,
      required: true
    }
  },  
  components: { Tag }
}
</script>

<template>
  <section>
    <span class="subtitulo-lg sua-lista-texto">
      Sua lista:
    </span>

    <ul class="ingredientes-sua-lista" v-if="ingredientes.length">
      <li v-for="(ingrediente, index) in ingredientes" :key="index">
        <Tag :texto="ingrediente" ativa/>
      </li>
    </ul>

    <p class="paragrafo lista-vazia" v-else>
      <img src="../assets/images/icones/lista-vazia.svg" alt="Icone de pesquisa">
      Sua lista esta vazia. Selecione ingredientes para iniciar.
    </p>
  </section>
</template>

<style scoped>

.sua-lista-texto {
  color: var(--coral, #F0633C);
  display: block;
  text-align: center;
  margin-bottom: 1.5rem;
}

.ingredientes-sua-lista {
  display: flex;
  justify-content: center;
  gap: 1rem 1.5rem;
  flex-wrap: wrap;
}

.lista-vazia {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 0.25rem;

  color: var(--coral, #F0633C);
  text-align: center;
}

</style>