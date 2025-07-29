<template>
  <div style="max-width: 420px;">
    <q-carousel v-if="projetos.length" v-model="slide" transition-prev="slide-right" transition-next="slide-left"
      swipeable animated navigation padding height="auto" arrows control-color="primary"
      class="bg-transparent no-border">

      navigation padding height="auto" arrows control-color="primary" class="bg-transparent no-border">
      <q-carousel-slide v-for="(projeto, index) in projetos" :key="index" :name="projeto.nome"
        class="column items-center q-px-md q-pt-md q-pb-lg">

        <q-card class="my-card q-pa-md bg-transparent border border-primary border-2"
          style="width: 100%; max-width: 320px; border-radius: 20px; overflow: hidden; background: white;">
          <img :src="projeto.img" :alt="projeto.titulo" class="imagem-projeto" />
          <q-card-section class="text-center">
            <div class="text-h6 text-weight-bold q-mb-xs">{{ projeto.titulo }}</div>
            <div class="text-caption text-grey q-mb-sm">{{ projeto.autor }}</div>
            <div class="text-subtitle2 text-grey-6">{{ projeto.descricao }}</div>

            <template v-if="projeto.nome === 'portfolio'">
              <q-btn icon="open_in_full" class="text-secondary q-mt-md" label="Ver Mais"
                style="background-color: var(--q-primary); border-radius: 8px;" />
            </template>
            <template v-else>
              <q-btn icon="open_in_full" :color="projeto.cor" :class="projeto.textColor" class="q-mt-md"
                label="Ver mais" style="border-radius: 8px;" />
            </template>

          </q-card-section>
        </q-card>

      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const slide = ref('estudy')

const projetos = [
  {
    nome: 'estudy', titulo: 'E-Study', autor: 'Desenv. Em Equipe', img: '/icons/estudy/loginEstudy.png',
    descricao: 'Plataforma Educacional de Estudos/Aprendizado online.',
    cor: 'indigo-5', textColor: 'text-white'
  },
  {
    nome: 'negomaq', titulo: 'NegoMaq Couros', autor: 'Desenv. Em Equipe', img: '/icons/estudy/negomaq.png',
    descricao: 'Sistema de Venda de Facas, Artigos de Couro e Churrasco',
    cor: 'negative', textColor: 'text-white'
  },
  {
    nome: 'portfolio', titulo: 'Portfolio Pessoal', autor: 'by Ezequiel Muller', img: '/icons/logocompleta.png',
    descricao: 'Meu Portfolio Pessoal.',
    cor: 'primary', textColor: 'text-secondary'
  }
]
</script>

<style scoped>
.imagem-projeto {
  width: 100%;
  height: 180px;
  object-fit: cover;
  border-radius: 12px;
  margin-bottom: 12px;
}

.q-carousel__control--type__navigation .q-btn--active {
  background-color: #1976d2 !important;
  transform: scale(1.4);
  opacity: 1;
}
</style>
