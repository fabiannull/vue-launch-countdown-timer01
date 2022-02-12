<template>
  <div id="app">
    <CountDownTimer></CountDownTimer>
  </div>
</template>

<script>
import CountDownTimer from './components/CountDownTimer.vue';

export default {
  name: 'App',
  components: { CountDownTimer },
  data: function () {
    return {};
  },
};
</script>

<style>
*,
*:before,
*:after {
  box-sizing: inherit;
  margin: 0;
  padding: 0;
}

:root {
  box-sizing: border-box;
  text-size-adjust: none;
  -webkit-text-size-adjust: none;
  position: relative;
  font-family: system-ui, 'Apple Color Emoji', 'Segoe UI Emoji',
    'Segoe UI Symbol', 'Noto Color Emoji';
  min-height: 100%;
}
body {
  position: relative;
  height: 100%;
  min-height: 100vh;
  font-size: 100%;
  line-height: 1.5;
}

input,
textarea,
button {
  font-size: inherit;
  font-family: inherit;
}
</style>
