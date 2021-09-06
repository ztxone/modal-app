<template>
  <div
    @click.self="closeModal"
    class="backdrop top-0 fixed bg-black opacity-50 w-full h-full"
  >
    <div class="modal w-96 p-5 my-24 mx-auto bg-white rounded-xl text-center">
      <slot></slot>
      <div class="flex justify-evenly py-10">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["header", "theme"],
  methods: {
    closeModal() {
      this.$emit("close")
    },
  },
}
</script>
