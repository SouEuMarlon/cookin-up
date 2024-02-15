<script lang="ts">
  export default {
    props: {
      texto: {
        type: String,
        required: true
      },
      ativa: Boolean
    }
  }
</script>

<template>
  <span :class="['tag', { ativa }]">
    {{ texto }}
  </span>
</template>

<style scoped>
.tag {
  background: var(--cinza-claro);
  border-radius: 0.5rem;
  color: var(--cinza);
  display: inline-block;
  font-weight: 400;
  min-width: 4.25rem;
  padding: 0.5rem;
  text-align: center;
  transition: 0.2s;
}

.tag.ativa {
  color: var(--creme, #FFFAF3);
  background: var(--coral, #F0633C);
  font-weight: 700;
}


</style>