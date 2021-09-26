<template>
  <div class="page p-8">
    <modal-dialog :show="showModal" @closeModal="showModal = false">
      <template #content>
        <p class="mb-4">Gokuu is ...</p>
        <img class="w-full" src="https://i.gifer.com/QjMQ.gif" alt="" />
      </template>
      <template #caption="dummiesData">
        <p>{{ dummiesData.caption }}</p>
      </template>
    </modal-dialog>
    <button
      class="
        mx-auto
        w-full
        flex
        justify-center
        rounded-md
        border border-gray-300
        shadow-sm
        px-4
        py-2
        bg-white
        text-base
        font-medium
        text-grey-700
        hover:bg-gray-50
        focus:outline-none focus:ring-1 focus:ring-indigo-500
        sm:mt-0 sm:ml-3 sm:w-auto sm:text-sm
      "
      @click="showModal = true"
    >
      Open Modal
    </button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ModalDialog from './components/ModalDialog.vue'

const showModal = ref(false)
</script>
