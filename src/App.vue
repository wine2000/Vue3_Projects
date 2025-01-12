<template>
  <div>
    <h1>Hi There</h1>

    <div v-if="showModal">
      <MyModal theme="theme" @close="showModal=false">
      <h1>Login successful</h1>
      <p>Our Welcome pages</p>
      
      <template v-slot:Links>
      <a href="">Sign Up</a>
      <a href="">Login</a>
      </template> 
      </MyModal>

    </div>
    <button @click="showModal = true">Close</button>
  </div>
</template>

<script>
import MyModal from "./components/MyModal.vue";

export default {
  data() {
    return {
      header: "Login Successful",
      content: "Welcome Our Pages",
      theme: "success",
      showModal: false,
    };
  },
  components: {
    MyModal,
  },
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>
