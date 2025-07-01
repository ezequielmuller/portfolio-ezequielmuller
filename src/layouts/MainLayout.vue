<template>
  <q-layout view="lHh Lpr lFf" class="bg-secondary">
    <q-header elevated
      style="max-width: 1000px; width: 100%; margin: 0 auto; border-radius: 0 0 20px 20px; overflow: hidden">
      <q-toolbar class="bg-white text-black q-pa-md">
        <q-btn flat dense round icon="menu" aria-label="Menu" />

        <q-toolbar-title class="text-center text-primary"> Portfólio </q-toolbar-title>

        <div class="row items-center q-gutter-sm">
          <q-btn flat dense round icon="mdi-whatsapp" aria-label="WhatsApp" @click="goTo('https://wa.me/SEUNUMERO')" />
          <q-btn flat dense round icon="mdi-linkedin" aria-label="LinkedIn"
            @click="goTo('https://www.linkedin.com/in/SEULINK/')" />
          <q-btn flat dense round icon="mdi-instagram" aria-label="Instagram"
            @click="goTo('https://instagram.com/SEUINSTAGRAM')" />
          <q-btn flat dense round icon="mdi-github" aria-label="GitHub" @click="goTo('https://github.com/SEUGITHUB')" />
          <q-btn flat dense round icon="mdi-email" aria-label="Email" @click="goTo('mailto:SEUEMAIL@example.com')" />
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
