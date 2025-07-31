<template>
  <q-page padding>
    <div class="q-mt-md q-px-sm">
      <div class="q-gutter-md row items-center justify-center q-col-gutter-md">

        <div class="text-primary text-center flex flex-center"
          :class="$q.platform.is.mobile ? 'text-h6 col-5 ' : 'text-h4 col-3'" style="font-weight: bold;">
          <div>
            <span class="text-grey-7" style="font-family: monospace;">&lt;</span>
            <span class="text-primary">Ezequiel Henrique Gazolla Muller</span>
            <span class="text-grey-7" style="font-family: monospace;">/&gt;</span>
          </div>
        </div>

        <div class="flex flex-center">
          <q-img src="icons/foto_perfil.jpg" alt="Foto de Perfil" :style="{
            width: $q.platform.is.mobile ? '190px' : '270px',
            height: $q.platform.is.mobile ? '190px' : '270px',
            borderRadius: '15px',
            border: '2px solid ',
          }" class="shadow-8" />
        </div>
      </div>
    </div>

    <q-separator color="grey" class="q-mx-md q-my-md" />

    <div v-if="$q.screen.lt.md">
      <div class="row flex flex-center text-h6 text-bold">Sobre mim</div>
      <SobreComponent id="sobreMobile" />
      <q-separator color="grey" class="q-mx-md q-my-md" />

      <div class="row flex flex-center text-h6 text-bold">Formações</div>
      <ExperienciaComponent />
      <q-separator color="grey" class="q-mx-md q-my-md" />
    </div>

    <div v-else>
      <div class="row q-col-gutter-md items-start">
        <div class="col-6">
          <div class="row flex flex-center text-h6 text-bold">Sobre mim</div>
          <SobreComponent />
        </div>
        <div class="col-6">
          <div class="row flex flex-center text-h6 text-bold">Formações</div>
          <ExperienciaComponent />
        </div>
      </div>
      <q-separator color="grey" class="q-mx-md q-my-md" />
    </div>

    <div class="row flex flex-center text-h6 text-bold">Habilidades</div>
    <HabilidadesComponent />
    <q-separator color="grey" class="q-mx-md q-my-md" />

    <div class="row flex flex-center text-h6 text-bold">Projetos</div>
    <ProjetosComponent />
    <q-separator color="grey" class="q-mx-md q-my-md" />

    <div class="row flex flex-center text-h6 text-bold">Entre em Contato</div>
    <ContatoComponent class="q-mt-md q-mb-mt" />

  </q-page>
</template>

<script setup lang="ts">
import { useQuasar } from 'quasar';
import SobreComponent from 'src/components/SobreComponent.vue';
import ExperienciaComponent from 'src/components/ExperienciaComponent.vue';
import HabilidadesComponent from 'src/components/HabilidadesComponent.vue';
import ProjetosComponent from 'src/components/ProjetosComponent.vue';
import ContatoComponent from 'src/components/ContatoComponent.vue';

const $q = useQuasar();
</script>
