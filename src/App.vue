<template>
  <div class="flex flex-col items-center justify-center h-screen z-0">
    <h1 class="text-2xl font-bold py-10">{{ title }}</h1>
    <teleport to=".modals">
      <Modal v-if="showModal" class="z-10" @close="toggleModal">
        <h1
          :class="{ ['text-white' + ' ' + 'bg-gray-800']: theme === 'dark' }"
          class="text-xl"
        >
          Hello Modal from div #app
        </h1>
        <p>modal content</p>
        <template v-slot:links>
          <a href="#" class="p-4 bg-red-200 rounded-xl">Sing Up</a>
          <a href="#" class="p-4 bg-red-200 rounded-xl">More info</a>
        </template>
      </Modal>
    </teleport>

    <button @click="toggleModal" class="rounded-xl bg-red-100 p-4">
      Open Modal
    </button>
  </div>
</template>

<script>
import Modal from "./components/Modal.vue"

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "Modal App with Teleport feature",
      showModal: false,
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
  },
}
</script>

<style></style>
