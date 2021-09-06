<template>
  <div class="flex flex-col items-center justify-center">
    <h1 class="text-2xl font-bold">{{ title }}</h1>
    <teleport to=".modals">
      <Modal v-if="showModal" class="z-10" @close="toggleModal">
        <h1
          :class="{ ['text-white' + ' ' + 'bg-gray-800']: theme === 'dark' }"
          class="text-xl"
        >
          First App
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
      title: "First App",
      showModal: false,
    }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add("active")
      this.$refs.name.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
  },
}
</script>

<style></style>
