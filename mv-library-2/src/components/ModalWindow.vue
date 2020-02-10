<template>
  <div class="overlay" v-show="isOpen">
    <div class="modal_window">
      <div class="close_button" @click="toClose">&times;</div>
      <h2>Title</h2>
      <p>{{isOpen}}</p>
      <slot class="content"></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: {
      type: Boolean
    }
  },  
  methods: {
    toClose() {      
      console.log(this.Open);
      this.$emit("toClose", false);
    }
  }
};
</script>
<style>
.overlay {
  display: block;
  position: fixed;
  top: 0;
  /* overflow: hidden; */
  margin: 0;
  padding: 0;
  border: none;
  width: 100vw;
  height: 100vh;
  background-color: #383940f2;
  z-index: 1100;
}
.modal_window {
  display: block;
  width: 75vw;
  max-width: 1200px;
  min-height: 80vh;
  margin: auto;
  margin-top: 7vh;
  position: relative;
  padding: 30px;
  background-color: white;
  color: #1e1e1e;
  border: none;
  border-radius: 3px;
}
.close_button {
  color: #ffffff;
  background-color: #c3c3c3;
  /* border: 1px solid #1e1e1e; */
  border-radius: 50%;
  position: absolute;
  top: 10px;
  line-height: 35px;
  font-size: 35px;
  right: 10px;
  height: 40px;
  width: 40px;
  cursor: pointer;
}
</style>