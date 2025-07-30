<template>
  <q-layout style="width: 100%;" view="lHh Lpr lFf" class="bg-secondary">
    <q-header elevated class="liquid-glass"
      style="background-color: rgba(30, 30, 30, 0.3); box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);">

      <q-toolbar class="text-primary q-pb-md q-pt-md row">
        <q-btn flat round dense icon="menu">
          <q-menu anchor="bottom right" self="top right" class="liquid-glass" transition-show="jump-down"
            style="background-color: rgba(255, 255, 255, 0.08);" transition-hide="jump-up">
            <q-list style="min-width: 150px;" class="text-primary">
              <q-item clickable v-ripple>
                <q-item-section class="text-primary">Home</q-item-section>
              </q-item>
              <q-item clickable v-ripple>
                <q-item-section class="text-primary">Sobre</q-item-section>
              </q-item>
              <q-item clickable v-ripple>
                <q-item-section class="text-primary">Habilidades</q-item-section>
              </q-item>
              <q-item clickable v-ripple>
                <q-item-section class="text-primary">Projetos</q-item-section>
              </q-item>
              <q-item clickable v-ripple>
                <q-item-section class="text-primary">Contato</q-item-section>
              </q-item>
            </q-list>
          </q-menu>
        </q-btn>

        <q-separator vertical class="q-ml-md bg-primary" />

        <q-toolbar-title class="text-center text-bold text-primary " style="padding-left: 0; letter-spacing: 1px;">
          Ezequiel Muller
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container style="padding-top: 15px;">
      <q-toggle v-model="tema" checked-icon="mdi-weather-night" unchecked-icon="mdi-white-balance-sunny" color="primary"
        icon-color="secondary" size="60px" style="position: fixed; bottom: 16px; left: 8px; z-index: 1000;" />

      <IndexPage />

    </q-page-container>


    <div v-if="tema === true" class="bg-grey-10 text-white q-pa-md q-mt-md"
      style="bottom: 0; width: 100%; text-align: center; font-size: 12px; z-index: 1000; border-top: 1px solid grey">
      © 2025 Ezequiel Muller. Todos os direitos reservados.
    </div>

    <div v-else class="bg-primary text-white q-pa-md q-mt-md"
      style="bottom: 0; width: 100%; text-align: center; font-size: 12px; z-index: 1000;">
      © 2025 Ezequiel Muller. Todos os direitos reservados.
    </div>
  </q-layout>

</template>

<script setup lang="ts">
import { useQuasar, setCssVar } from 'quasar'
import { ref, watch, onMounted } from 'vue'
import IndexPage from 'src/pages/IndexPage.vue'
// import NormalPage from 'src/pages/NormalPage.vue'

const $q = useQuasar()
// const mobile = computed(() => $q.screen.lt.sm)

const tema = ref(localStorage.getItem('tema') === 'true')

function aplicarTema(escuro: boolean) {
  $q.dark.set(escuro)
  localStorage.setItem('tema', escuro.toString())
  setCssVar('primary', escuro ? '#e9e9e9' : '#1e1e1e')
  setCssVar('secondary', escuro ? '#1e1e1e' : '#e9e9e9')
  console.log("TEMA APLICADO=>>", escuro)
}

watch(tema, (valor) => {
  aplicarTema(valor)
})

onMounted(() => {
  aplicarTema(tema.value)
})
</script>
