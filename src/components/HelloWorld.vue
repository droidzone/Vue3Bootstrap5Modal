<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <h3>Test Bootstrap Modal</h3>
    <bootstrap-modal :showModal="showModalNow" @closeModal="closeMyModal"></bootstrap-modal>
    <a href="#" @click="toggleModal">now</a>
  </div>
</template>

<script>
import BootstrapModal from "./BootstrapModal.vue"
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  components: {
    "bootstrap-modal": BootstrapModal,
  },
  data() {
    return {
      showModalNow: false,
    }
  },
  methods: {
    closeMyModal() {
      this.showModalNow = false;
    },
    toggleModal() {
      this.showModalNow = !this.showModalNow;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
