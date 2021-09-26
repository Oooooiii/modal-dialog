<template>
  <div class="page p-8">
    <modal-dialog :show="showModal" @closeModal="showModal = false">
      <p class="mb-4">Gokuu is ...</p>
      <img class="w-full" src="https://i.gifer.com/QjMQ.gif" alt="" />
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
      @click="toggleModal"
    >
      Open Modal
    </button>
  </div>
</template>

<script>
import { ref } from 'vue'
import ModalDialog from './components/ModalDialog.vue'

export default {
  name: 'App',
  components: {
    ModalDialog,
  },
  setup() {
    const showModal = ref(false)

    function toggleModal() {
      showModal.value = !showModal.value
    }

    return { showModal, toggleModal }
  },
}
</script>
