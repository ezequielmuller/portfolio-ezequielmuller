<template>
  <q-page padding>
    <div class=" row justify-between q-col-gutter-xs q-m-mt q-mx-xs">
      <div class="text-h6 text-bold text-primary text-center flex flex-center col-6 ">
        {{ tag + 'Ezequiel Henrique Gazolla Muller />' }}
      </div>
      <div class="col-6 text-center">
        <img src="icons/foto_perfil.jpg" alt="Foto de Perfil" class="q-mr-lg shadow-8 border-2px border-primary"
          style="width: 170px; height: 170px; border-radius: 20px;" />

      </div>
    </div>

    <q-separator color="grey" class="q-mx-md q-my-md" />

    <div class="row flex flex-center text-h6 text-bold">Sobre mim</div>
    <SobreMobile id="sobreMobile" />
    <q-separator color="grey" class="q-mx-md q-my-md" />

    <div class="row flex flex-center text-h6 text-bold">Formações</div>
    <ExperienciaMobile />
    <q-separator color="grey" class="q-mx-md q-my-md" />

    <div class="row flex flex-center text-h6 text-bold">Habilidades</div>
    <HabilidadesMobile />
    <q-separator color="grey" class="q-mx-md q-my-md" />

    <div class="row flex flex-center text-h6 text-bold">Projetos</div>
    <ProjetosMobile />
    <q-separator color="grey" class="q-mx-md q-my-md" />

    <div class="row flex flex-center text-h6 text-bold">Entre em Contato</div>
    <ContatoMobile class="q-mt-md q-mb-mt" />

  </q-page>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import SobreMobile from 'src/components/SobreMobile.vue';
import ExperienciaMobile from 'src/components/ExperienciaMobile.vue';
import HabilidadesMobile from 'src/components/HabilidadesMobile.vue';
import ProjetosMobile from 'src/components/ProjetosMobile.vue';
import ContatoMobile from 'src/components/ContatoMobile.vue';

const tag = ref('');


onMounted(() => {
  tag.value = '<';
});
</script>
