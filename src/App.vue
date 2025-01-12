<template>
  <div>
    <h1>Hi There</h1>

    <div v-if="showModal">
      <MyModal :theme="theme" @close="showModal = false">
        <h1 id="show">Login successful</h1>
        <p>Our Welcome pages</p>
        <template v-slot:Links>
          <a href="">Sign Up</a>
          <a href="">Login</a>
          <slot />
        </template>
      </MyModal>
    </div>
    <div v-if="deleteModal">
      <MyModal theme="delete" @close="deleteModal = false">
        <h2>Are you want delete?</h2>
        <template v-slot:delete>
          <a href="">Yes</a>
          <a href="">No</a>
        </template>
      </MyModal>
    </div>
    <button @click="showModal = true">Open Modal</button>
    <button @click="deleteModal = true">Delete Modal</button>
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
      theme: "delete",
      showModal: false,
      deleteModal: false,
    };
  },
  components: {
    MyModal,
  },
};
</script>

<style scoped>
h1 {
  color: blue;
}
#show,
p {
  color: yellow;
}
</style>
