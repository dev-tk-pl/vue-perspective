<template>
  <div class="img-wrapper" @mousemove="getCursorPosition">
    <img
      :style="`transform: perspective(300px) rotateX(${x}deg) rotateY(${y}deg)`"
      alt="me"
      src="./assets/me.png"
    />
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      x: 0,
      y: 0,
    };
  },
  components: {},
  methods: {
    getCursorPosition(event) {
      // clientX/Y gives the coordinates relative to the viewport in CSS pixels.
      // console.log("clientX : " + event.clientX);
      // console.log("clientY : " + event.clientY);

      // pageX/Y gives the coordinates relative to the <html> element in CSS pixels.
      console.log((event.pageX / window.innerWidth).toFixed(2));
      console.log((event.pageY / window.innerHeight).toFixed(2));
     /* eslint-disable */
      this.y =
        ((event.pageX - window.innerWidth / 2) 
        / window.innerWidth).toFixed(2) * 34;
      this.x =
        ((event.pageY - window.innerHeight / 2) 
        / window.innerHeight).toFixed(2) * -34;

      // screenX/Y gives the coordinates relative to the screen in device pixels.
      // console.log("screenX : " + event.screenX);
      // console.log("screenY : " + event.screenY);
    },
  },
};
</script>

<style>
html,
body {
  padding: 0;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.img-wrapper {
  max-width: 100vw;
  min-height: 100vh;
  background: url("./assets/bg_home.jpg");
  display: flex;
  justify-content: center; /* align horizontal */
  align-items: center;
}
img {
  width: auto;
  height: 70vh;
  /* transform: perspective(300px) rotateX(20deg); */
}
</style>
