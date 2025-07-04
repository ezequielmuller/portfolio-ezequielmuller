<template>
  <q-page padding>
    <div class="row justify-between q-col-gutter-xs q-mt-md q-mb-mt">
      <div class="text-h6 text-white text-center flex flex-center col-6">
        {{ tag + 'PAGINA NORMAL />' }}
      </div>
      <div class="col-6 text-center">
        <img src="icons/foto_perfil.jpg" alt="Foto de Perfil" class="rounded-full q-mr-lg"
          style="width: 170px; height: 170px; border-radius: 40px; box-shadow: 0 8px 32px 0 rgba(0,0,0,0.5);" />
      </div>
    </div>

    <q-separator color="grey q-mx-md q-my-md" />

    <sobre />

  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';



const tag = ref('');

const onMounted = () => {
  tag.value = '<';
}
onMounted();
</script>
