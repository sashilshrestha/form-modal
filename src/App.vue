<template>
  <div>
    <div class="app-form-container">
      <AppForm @open-modal="toggleModalHandler"></AppForm>
    </div>
    <transition name="modal-transition">
      <app-modal
        @close-modal="toggleModalHandler"
        v-if="isModalOpen"
      ></app-modal>
    </transition>
  </div>
</template>

<script>
import AppForm from './components/AppForm.vue';
import AppModal from './components/AppModal.vue';

export default {
  name: 'App',
  components: { AppForm, AppModal },
  data() {
    return {
      isModalOpen: false,
    };
  },
  methods: {
    toggleModalHandler() {
      this.isModalOpen = !this.isModalOpen;
    },
  },
};
</script>

<style lang="scss" scoped>
.app-form-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.modal-transition-enter-active,
.modal-transition-leave-active {
  transition: opacity 0.3s ease;
}

.modal-transition-enter,
.modal-transition-leave-to {
  opacity: 0;
}
</style>
