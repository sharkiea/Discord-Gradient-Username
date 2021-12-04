<template>
  <div class="banner"></div>
  <div class="iframe">
    <iframe src="https://cssgradient.io/" frameborder="0"></iframe>
  </div>
  <GradientPicker/>
</template>

<script>
import GradientPicker from './components/GradientPicker.vue'

export default {
  name: 'App',
  components: {
    GradientPicker
  }
}
</script>

<style>
  @font-face {
    font-family: 'Whitney';
    src: url('./assets/whitney.ttf');
  }

  :root.theme-dark body {
    display: flex; justify-content: center;
    color: #dcddde;
    background-color: var(--background-tertiary); margin: 20px;
    font-family: 'Montserrat';
    transition: 500ms background-color;
  }

  #app {
    display: flex;
    flex-direction: column;
    width: 100vw;
    max-width: 800px;
  }

  .banner { 
    width: 100%; height: 200px;
    background: url('./assets/banner.png') center/cover;
    border-radius: 16px; margin-bottom: 20px;
  }

  .iframe { 
    height: 50vh;
    border-radius: 16px; 
    margin-bottom: 20px;
    overflow: hidden;
  }
  
  iframe { width: calc(100% + 18px); height: 100%;}

  @media (max-width: 600px) {
    iframe { width: 100%;}
  }

  ::-webkit-scrollbar { 
    display: block !important; background-color: var(--background-secondary) !important;
    width: 12px !important;
  }
  ::-webkit-scrollbar-corner { background-color: var(--background-secondary) !important;}
  ::-webkit-scrollbar-thumb { background-color: var(--background-primary) !important; border-radius: 0 !important;}
</style>