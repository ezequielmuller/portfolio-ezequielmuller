<template>
  <div class="q-pa-md">
    <div class="row q-gutter-md justify-center">
      <q-col v-for="lg in linguagens" :key="lg.nome" cols="4" sm="2"
        class="flex flex-center column items-center linguagem">
        <div class="linguagem-foto">
          <q-img :src="lg.img" style="width: 40px; height: 40px" contain />
        </div>
        <div class="linguagem-nome">
          {{ lg.nome }}
        </div>
      </q-col>
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
  { nome: 'JAVA', img: 'icons/java.png' },
  { nome: 'MySQL', img: 'icons/mysql.png' },
  { nome: 'PostgreSQL', img: 'icons/postgres.png' },
]
</script>


<style scoped>
.linguagem {
  transition: transform 0.3s ease;
}

.linguagem:hover {
  transform: translateY(-5px);
}

.linguagem-foto {
  width: 64px;
  height: 64px;
  background-color: #ffffff10;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  margin-bottom: 8px;
  transition: background-color 0.3s;
}

body.body--dark .linguagem-foto {
  background-color: #ffffff15;
}

.linguagem-nome {
  font-size: 14px;
  font-weight: 500;
  color: #ddd;
  text-align: center;
}

body.body--light .linguagem-nome {
  color: #333;
}
</style>
