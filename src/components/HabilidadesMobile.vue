<template>
  <div class="q-pa-md">
    <div class="row q-gutter-md justify-center">
      <q-card v-for="lg in linguagens" :key="lg.nome" class="card column items-center justify-between">
        <q-img :src="lg.img" style="width: 60px; height: 60px; margin-top: 12px" contain />
        <div class="titulo q-mb-sm">
          {{ lg.nome }}
        </div>
      </q-card>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Linguagem {
  nome: string
  img: string
}

const linguagens: Linguagem[] = [
  { nome: 'GIT', img: 'icons/git.png' },
  { nome: 'HTML', img: 'icons/html.png' },
  { nome: 'CSS', img: 'icons/css.png' },
  { nome: 'JavaScript', img: 'icons/javascript.png' },
  { nome: 'Vue.js', img: 'icons/vue.png' },
  { nome: 'React.js', img: 'icons/react.png' },
  { nome: 'Quasar', img: 'icons/quasar.png' },
  { nome: 'JAVA', img: 'icons/java.png' }
]
</script>

<style scoped>
.card {
  width: 100px;
  height: 120px;
  border: 1px solid rgba(0, 0, 0, 0.15);
  background-color: transparent;
  border-radius: 12px;
  transition: transform 0.2s;
  box-shadow: none;
  padding: 4px 0;
  text-align: center;
}

.card:hover {
  transform: scale(1.05);
}

body.body--dark .card {
  border-color: rgba(255, 255, 255, 0.2);
}

.titulo {
  font-size: 13px;
  font-weight: 500;
  color: #333;
}

body.body--dark .titulo {
  color: white;
}
</style>
