<template>
  <teleport to="body">
    <transition
      enter-active-class="transition ease-out duration-200 transform"
      enter-from-class="opacity-0"
      enter-to-class="opacity-100"
      leave-active-class="transition ease-in duration-200 transform"
      leave-from-class="opacity-100"
      leave-to-class="opacity-0"
    >
      <div
        v-show="showModal"
        ref="modal-backdrop"
        class="fixed z-10 inset-0 overflow-y-auto bg-black bg-opacity-50"
      >
        <div
          class="flex items-start justify-center min-h-screen pt-24 text-center"
        >
          <transition
            enter-active-class="transition ease-out duration-300 transform "
            enter-from-class="opacity-0 translate-y-10 scale-95"
            enter-to-class="opacity-100 translate-y-0 scale-100"
            leave-active-class="ease-in duration-200"
            leave-from-class="opacity-100 translate-y-0 scale-100"
            leave-to-class="opacity-0 translate-y-10 translate-y-0 scale-95"
          >
            <div
              v-show="showModal"
              ref="modal"
              class="
                relative
                bg-white
                rounded-lg
                text-left
                overflow-hidden
                shadow-xl
                p-8
                w-1/2
              "
              role="dialog"
              aria-modal="true"
              aria-labelledby="modal-headline"
            >
              <button class="absolute top-4 right-4">
                <i-mdi-close @click="$emit('closeModal')" />
              </button>
              <slot name="content">Empty Content</slot>
              <slot name="caption" :caption="dummiesData">Empty Caption</slot>
            </div>
          </transition>
        </div>
      </div>
    </transition>
  </teleport>
</template>

<script setup>
import { ref, watch } from 'vue'
import useClickOutside from '../composables/useClickOutside'

const showModal = ref(false)
const modal = ref(null)
const { onClickOutside } = useClickOutside()

const dummiesData = `Son Goku, born Kakarot, is a male Saiyan and the main protagonist of the
                  Dragon Ball metaseries created by Akira Toriyama. Fandom`

const props = defineProps({
  show: {
    type: Boolean,
    default: false,
  },
})

const emit = defineEmits(['closeModal'])

watch(
  () => props.show,
  (show) => {
    showModal.value = show
  }
)

onClickOutside(modal, () => closeModal())

function closeModal() {
  emit('closeModal')
}
</script>
