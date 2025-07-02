<template>
  <q-layout view="lHh Lpr lFf" class="bg-secondary">
    <q-header elevated
      style="max-width: 1000px; width: 100%; margin: 0 auto; border-radius: 0 0 20px 20px; overflow: hidden">
      <q-toolbar class="bg-white text-black q-pa-md">
        <img src="icons/foto_perfil.jpg" alt="Logo" class="q-mr-md"
          style="width: 60px; height: 60px; border-radius: 30px;" />
        <q-separator vertical class="q-ml-sm" color="primary" />
        <q-toolbar-title class="text-justify text-primary"> Ezequiel H. G. Muller </q-toolbar-title>

        <div class="row items-center q-gutter-sm">
          <q-btn flat dense round icon="mdi-whatsapp" aria-label="WhatsApp"
            @click="goTo('https://wa.me/54999228928')" />
          <q-btn flat dense round icon="mdi-linkedin" aria-label="LinkedIn"
            @click="goTo('https://www.linkedin.com/in/ezequielhgmuller/')" />
          <q-btn flat dense round icon="mdi-instagram" aria-label="Instagram"
            @click="goTo('https://instagram.com/ezequielmuller__')" />
          <q-btn flat dense round icon="mdi-github" aria-label="GitHub"
            @click="goTo('https://github.com/ezequielmuller')" />
          <q-btn flat dense round icon="mdi-email" aria-label="Email" @click="goTo('mailto:zikimuller017@gmail.com')" />
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view class="bg-secondary text-primary" />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
function goTo(url: string) {
  window.open(url, '_blank');
}
</script>
