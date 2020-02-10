<template>
  <div class="home">
    <modalWindow v-bind:isOpen="isOpen" @toClose="toClose">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Animi dolorum officiis ipsum odio minima itaque officia placeat dolorem. Fugiat maxime cumque odit nisi sunt possimus mollitia eaque eius expedita eligendi. 
    </modalWindow>
    <button
    @click="toOpen">Открыть окно</button>
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import modalWindow from '@/components/ModalWindow.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld,
    modalWindow
  },
  data(){
    return{
      isOpen: false
    }
  },
  methods:{
    toOpen(){
      this.isOpen = true;
      console.log(this.isOpen);
    },
    toClose(isOpen){
      this.isOpen = isOpen;
      console.log(this.isOpen);
    }
  }
}
</script>
