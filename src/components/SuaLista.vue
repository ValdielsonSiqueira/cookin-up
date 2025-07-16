<template>
  <section>
    <span class="subtitulo-lg titulo">
      {{ lista.titulo }}
    </span>
    
    <ul v-if="lista.ingredientes.length" class="item-lista">
      <li v-for="(ingrediente, index) in lista.ingredientes" :key="index">
        <Tag :texto="ingrediente" ativa />
      </li>
    </ul>

    <p v-else class="paragrafo lista-vazia">
      <img src="../assets/imagens/icones/lista-vazia.svg" alt="Ícone de uma lista vazia" class="icone-lista-vazia">
        {{ lista.placeholder }}
    </p>
  </section>
</template>

<script lang="ts">
import Tag from './Tag.vue';
import type ILista from '@/interfaces/ILista';
import type { PropType } from 'vue';

  export default {
    name: 'SuaLista',
    props: {
      lista: {
        type: { type: Object as PropType<ILista>, required: true },
      }
    },
    components: {
      Tag,
    },
  }
</script>

<style scoped>
.titulo {
  color: var(--coral, #F0633C);
  display: block;
  text-align: center;
  margin-bottom: 1.5rem;
}

.item-lista {
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