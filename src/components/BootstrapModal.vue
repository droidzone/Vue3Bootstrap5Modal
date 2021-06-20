<template>
  <teleport to="body">
    <div
      ref="modal"
      class="modal fade"
      :class="{ show: active, 'd-block': active }"
      tabindex="-1"
      role="dialog"
    >
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header bg-primary text-light">
            <h5 class="modal-title">Modal title</h5>
            <button
              type="button"
              class="close"
              data-dismiss="modal"
              aria-label="Close"
              v-on:click="$emit('closeModal')"
            >
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body bg-success text-dark">
            <p>Modal body text goes here.</p>
          </div>
          <div class="modal-footer bg-warning text-dark">
            <button type="button" class="btn btn-secondary" v-on:click="$emit('closeModal')">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>
  </teleport>
</template>

<script>
export default {
  name: "BootstrapModal",
  emits: ["closeModal"],
  props: {
    showModal: Boolean,
  },
  watch: {
    showModal: {
      handler(newVal) {
        this.active = newVal;
        const body = document.querySelector("body");
        this.showModal ? body.classList.add("modal-open") : body.classList.remove("modal-open")
      },
      immediate: true,
      deep: true,
    },
  },
  data() {
    return {
      active: this.showModal,
    };
  },
};
</script>

<style lang="scss" scoped></style>
