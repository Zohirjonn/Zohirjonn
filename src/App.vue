<template>
  <div class="container">
    <h1>This is app vue</h1>
    <div class="btn">
      <button @click="openHello">Open</button>
    </div>
    <HelloWorld v-if="isOpen" @yopish="closeBtn" />
    <TwoWorld />
    <SignIn />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import TwoWorld from "./components/TwoWorld.vue";
import SignIn from "./components/SingIn.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    TwoWorld,
    SignIn,
  },
  data() {
    return {
   
      isOpen: false,
    };
  },
  methods: {
    openHello() {
      this.isOpen = true;
    },
    closeBtn() {
      this.isOpen = false;
    },
  },
};
</script>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.btn {
  display: flex;
  justify-content: center;
  margin-bottom: 1rem;
}
h1 {
  width: 30%;
  margin: 1rem auto;
  padding: 1rem;
  border-radius: 5px;
  background: rgb(63, 94, 251);
  background: radial-gradient(
    circle,
    rgba(63, 94, 251, 1) 65%,
    rgba(70, 168, 252, 1) 100%
  );
  color: white;
  box-shadow: rgba(0, 0, 0, 0.17) 0px -23px 25px 0px inset,
    rgba(0, 0, 0, 0.15) 0px -36px 30px 0px inset,
    rgba(0, 0, 0, 0.1) 0px -79px 40px 0px inset, rgba(0, 0, 0, 0.06) 0px 2px 1px,
    rgba(0, 0, 0, 0.09) 0px 4px 2px, rgba(0, 0, 0, 0.09) 0px 8px 4px,
    rgba(0, 0, 0, 0.09) 0px 16px 8px, rgba(0, 0, 0, 0.09) 0px 32px 16px;
}
button {
  padding: 0.5rem 2rem;
  font-size: 20px;
  margin-left: 1rem;
  color: white;
  background: rgb(2, 228, 250);
  background: radial-gradient(
    circle,
    rgba(33, 54, 244, 0.958) 28%,
    rgb(69, 25, 242) 100%
  );
  border: none;
  border-radius: 5px;
  box-shadow: rgba(0, 0, 0, 0.17) 0px -23px 25px 0px inset,
    rgba(0, 0, 0, 0.15) 0px -36px 30px 0px inset,
    rgba(0, 0, 0, 0.1) 0px -79px 40px 0px inset, rgba(0, 0, 0, 0.06) 0px 2px 1px,
    rgba(0, 0, 0, 0.09) 0px 4px 2px, rgba(0, 0, 0, 0.09) 0px 8px 4px,
    rgba(0, 0, 0, 0.09) 0px 16px 8px, rgba(0, 0, 0, 0.09) 0px 32px 16px;
  margin: 0 auto;
}
button:active {
  transform: scale(1.1);
  border: none;
}
</style>
