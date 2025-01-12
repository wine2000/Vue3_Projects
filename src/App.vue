<template>
  <div>
    <h1>Hi There</h1>
    <MyModal header="Login Successful" content="Welcome Our Pages" theme="delete"/>
  </div>
</template>

<script>
import MyModal from "./components/MyModal.vue";

export default {
  data(){
    return{

    }
  },
  components: {
    MyModal,
  },
};
</script>

<style scoped>
h1{
  color:red
}
</style>
