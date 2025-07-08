<template>
  <!-- ===== LAYOUT NORMAL ===== -->
  <q-layout v-if="!mobile" view="lHh Lpr lFf" class="bg-primary">
    <q-header class="bg-primary"
      style="max-width: 900px; margin: 24px auto 0 auto; border-radius: 24px; box-shadow: 0 2px 12px rgba(0,0,0,0.08);">

      <q-toolbar class="bg- text-white q-pa-md">
        <img src="icons/foto_perfil.jpg" alt="Logo" class="q-mr-md"
          style="width: 60px; height: 30px; border-radius: 30px;" />
        <q-separator vertical class="q-ml-sm" color="white" />
        <q-toolbar-title class="text-justify text-white"> Ezequiel Muller - Web Developer </q-toolbar-title>
        <!-- <div class="row items-center q-gutter-sm">
          <q-btn flat dense round icon="mdi-linkedin" aria-label="LinkedIn"
            @click="goTo('https://www.linkedin.com/in/ezequielhgmuller/')" />
          <q-btn flat dense round icon="mdi-instagram" aria-label="Instagram"
            @click="goTo('https://instagram.com/ezequielmuller__')" />
          <q-btn flat dense round icon="mdi-github" aria-label="GitHub"
            @click="goTo('https://github.com/ezequielmuller')" />
          <q-btn flat dense round icon="mdi-email" aria-label="Email" @click="goTo('mailto:zikimuller017@gmail.com')" />
        </div> -->
      </q-toolbar>
      <q-separator color="grey" class="q-mr-md q-ml-md" />
    </q-header>

    <q-page-container>
      <NormalPage class="bg-secondary2 text-primary" />
    </q-page-container>
  </q-layout>

  <!-- ===== LAYOUT MOBILE ===== -->
  <q-layout v-else style="width: 100%;" view="lHh Lpr lFf" class="bg-primary">
    <q-header>
      <q-toolbar class="bg-primary text-white   q-pb-md q-pt-md row">
        <q-btn flat round dense icon="menu">
          <q-menu anchor="bottom right" self="top right">
            <q-list style="min-width: 150px; border: 2px solid #454545;" class="bg-primary text-white">
              <q-item clickable v-ripple>
                <q-item-section>Home</q-item-section>
              </q-item>
              <q-item clickable v-ripple>
                <q-item-section>Sobre</q-item-section>
              </q-item>
              <q-item clickable v-ripple>
                <q-item-section>Habilidades</q-item-section>
              </q-item>
              <q-item clickable v-ripple>
                <q-item-section>Projetos</q-item-section>
              </q-item>
              <q-item clickable v-ripple>
                <q-item-section>Contato</q-item-section>
              </q-item>
            </q-list>
          </q-menu>
        </q-btn>

        <q-separator vertical color="grey-8" class="q-ml-md" />

        <q-toolbar-title class="text-center text-white" style="padding-left: 0;">Ezequiel Muller - Web
          Developer</q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <MobilePage class="bg-secondary2 text-primary" />
    </q-page-container>
  </q-layout>

</template>

<script setup lang="ts">
import { useQuasar } from 'quasar';
import { computed } from 'vue';
import MobilePage from 'src/pages/MobilePage.vue';
import NormalPage from 'src/pages/NormalPage.vue';

const $q = useQuasar();
const mobile = computed(() => $q.screen.lt.sm);

// function goTo(url: string) {
//   window.open(url, '_blank');
// }
</script>
