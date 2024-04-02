<template>
  <q-page padding>
    <q-table title="Treats" :rows="posts" :columns="columns" row-key="name" />
  </q-page>
</template>

<script setup lang="ts">
import { defineComponent, ref } from 'vue';

interface Post {
  id: number;
  title: string;
  views: number;
  content: string;
}

export default defineComponent({
  name: 'IndexPage',
  setup() {
    const columns = [
      { name: 'id', label: 'Id', field: 'id', sortable: true },
      { name: 'title', label: 'Titulo', field: 'title', sortable: true },
      { name: 'views', label: 'Visualizacoes', field: 'views', sortable: true },
      { name: 'content', label: 'Conteudo', field: 'content', sortable: true }
    ];

    const posts = ref<Post[]>([]);

    return { posts, columns };
  }
});
</script>