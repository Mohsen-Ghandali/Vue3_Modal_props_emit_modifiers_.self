<template>
  <main>
    <h1>{{ title }}</h1>
    <div v-if="showModal">
      <Modal :hiModal='hiModal' :textModal='textModal' @close-modal="changeModal" />
    </div>
    <button @click="changeModal">Show Modal</button>
  </main>
</template>

<script lang="ts">
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },

  data() {
    return {
      title: "Hallo-Welt",
      hiModal:'Hello-Modal',
      textModal:'Modal Content',
      showModal: false,
    };
  },

  methods: {
     changeModal(this: any): void {
      this.showModal=!this.showModal
     },
  },
};
</script>

<style scoped lang="scss">
main {
  margin: 0 auto;
  text-align: center;
  h1 {
    font: bold 32px arial;
    text-align: center;
    margin: 68px 0;
  }
  button {
    padding: 6px 16px;
    border-radius: 4px;
    margin-left: 4px;
    border: none;
    cursor: pointer;
    background-color: blueviolet;
    color: #ebebeb;
  }
}
</style>
