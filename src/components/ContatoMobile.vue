<template>
  <div class="row q-col-gutter-sm q-mx-md"
    style="border: 2px solid grey; padding: 12px; border-style:solid; border-radius: 20px;">
    <div class="col-md-12 col-sm-12 col-xs-12">
      <q-input v-model="nome" outlined dense label="Nome Completo" clearable>
        <template v-slot:prepend>
          <q-icon name="person" />
        </template>
      </q-input>
    </div>
    <div class="col-md-12 col-sm-12 col-xs-12 ">
      <q-input v-model="email" outlined dense label="Email" clearable>
        <template v-slot:prepend>
          <q-icon name="attach_email" />
        </template>
      </q-input>
      <span class="text-grey flex flex-center">exemplo@gmail.com</span>
    </div>
    <div class="col-md-12 col-sm-12 col-xs-12 ">
      <q-input v-model="assunto" outlined dense label="Assunto" clearable>
        <template v-slot:prepend>
          <q-icon name="connect_without_contact" />
        </template>
      </q-input>
    </div>
    <div class="col-md-12 col-sm-12 col-xs-12 ">
      <q-input v-model="mensagem" outlined dense label="Mensagem" type="textarea" clearable>
        <template v-slot:prepend>
          <q-icon name="mark_unread_chat_alt" />
        </template>
      </q-input>
    </div>
    <div class="col-md-12 col-sm-12 col-xs-12" align="right">
      <q-btn icon="send" class="text-secondary q-ml-sm" label="Enviar"
        style="background-color: var(--q-primary); border-radius: 8px;" />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const nome = ref('')
const email = ref('')
const assunto = ref('')
const mensagem = ref('')
</script>
