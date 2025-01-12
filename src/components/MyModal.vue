<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{success:theme==='success',danger:theme==='delete'}">
      <!-- <h1>{{header}}</h1>
      <p class="p">{{content}}</p> -->
      <slot>default</slot>
      <slot name="Links"/>

    </div>
  </div>
</template>

<script>
export default {
  props:['theme'],
  methods:{
    closeModal(){
    this.$emit("close")
    }
  }
};
</script>

<style>
.backdrop {
  background: gray;
  position: fixed;
  width: 100%;
  height: 100%;
}
.modal {
  background-color: cadetblue;
  width: 400px;
  padding: 40px;
  margin: 100px auto;
  border-radius: 10px;
}
.p{
  font-style: normal;
}
.success{
  background-color: rgb(42, 215, 42);
  color: black;
}
.danger{
  background-color: red;
  color:white;
}
</style>