<template>
  <div>
    {{ categoria.nome }}
    {{ categoria.imagem }}
  </div>
</template>

<script lang="ts">
import type ICategoria from '@/interfaces/ICategoria';
import type { PropType } from 'vue';

export default {
  name: 'CardCategoria',
  props: {
    categoria: {
      type: { type: Object as PropType<ICategoria>, required: true },
    }
  }
}
</script>

