<template>
  <div>
    <div class="banner"></div>
    <div class="iframe">
      <iframe src="https://cssgradient.io/" frameborder="0"></iframe>
      
    </div>
    <GradientPicker/>
  </div>
  <video controls>
      <source src="./assets/tutorial.mp4"
              type="video/mp4">
  </video>
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
    display: flex; justify-content: center;
    width: 100vw; gap: 20px;
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

  video { 
    width: 100%; max-width: 600px; min-width: 0;
    position: sticky; top: calc(25% - 10px);
    height: fit-content;
    border-radius: 16px;
  }

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