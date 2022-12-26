<template>
  <div class="container">
    <button @click="closeBtn">close</button>
  </div>
  <h1>This is Header component.</h1>
</template>

<script>
export default {
  name: "HelloWorld",
  methods: {
    closeBtn() {
      this.$emit("yopish");
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* template {
  display: flex;
  justify-content: center;
} */
.container {
  display: flex;
  justify-content: center;
}
button {
  padding: 0.5rem 2rem;
  border: none;
  font-size: 20px;
  margin-left: 1rem;
  background: rgb(2, 228, 250);
  background: radial-gradient(
    circle,
    rgba(250, 101, 2, 0.958) 28%,
    rgb(249, 164, 6) 100%
  );
  color: white; 
  border-radius: 5px;
  box-shadow: rgba(0, 0, 0, 0.17) 0px -23px 25px 0px inset,
    rgba(0, 0, 0, 0.15) 0px -36px 30px 0px inset,
    rgba(0, 0, 0, 0.1) 0px -79px 40px 0px inset, rgba(0, 0, 0, 0.06) 0px 2px 1px,
    rgba(0, 0, 0, 0.09) 0px 4px 2px, rgba(0, 0, 0, 0.09) 0px 8px 4px,
    rgba(0, 0, 0, 0.09) 0px 16px 8px, rgba(0, 0, 0, 0.09) 0px 32px 16px;
  margin: 0 1rem;
}
button:active {
  transform: scale(1.1);
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
</style>
