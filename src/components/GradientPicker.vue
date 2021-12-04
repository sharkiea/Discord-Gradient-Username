<template>
  <div class="content">
    <header>
      <link :href="themeLink" rel="stylesheet">
      <div class="title">
        <h3>Thanks again for donating to me </h3>
        <img src="../assets/peepolove.png" alt="peepoLove">
      </div>
      <h4>Use the CSS gradient website upper and copy the result in the gradient field</h4>
      <div class="choices">
        <input type="text" v-model="username" placeholder="Enter your username">
        <input type="text" v-model="gradient" placeholder="Enter your gradient">
        <div class="themes">
          <img src="../assets/comfy.png" alt="Comfy" v-on:click="theme = 'comfy'">
          <img src="../assets/lilypichu.png" alt="LilyPichu" v-on:click="theme = 'lilypichu'">
          <img src="../assets/couve.png" alt="Couve" v-on:click="theme = 'couve'">
        </div>
      </div>
    </header>

    <main>
      <div class="profileCustomizationSection-1-Issy">
        <div class="baseLayout-NX_bpH">
          <div class="profileBannerPreview-gaX5MP">
            <div class="bannerNormal-3u-o59 banner-3vVQWW" style="background-color: rgb(217, 198, 181);"></div>
            <div class="avatarUploader-3XDtmn avatarUploaderNormal-1kvMcd avatarUploader-3h7Odh">
              <div class="avatarUploaderInner-3UNxY3 avatarUploaderInner-mAGe3e" style="background-image: url(&quot;https://cdn.discordapp.com/avatars/265924886461939712/1414ce40448adcd9fcf7225a8e0936ac.webp?size=80&quot;);"></div>
            </div>
            <div class="headerTop-3vNv-a">
              <div class="profileBadges-ohc0Vu container-q03LZO" aria-label="Badges d'utilisateur" role="group">
                <div class="clickable-17BDii" aria-label="Balance de la HypeSquad" role="button" tabindex="0">
                  <img alt=" " aria-hidden="true" src="../assets/hypesquad.svg" class="profileBadge22-LJmn9o profileBadge-2niAfJ desaturate-qhyunI">
                </div>
              </div>
              <div class="headerText-1vVs-U">
                <div class="headerTagNoNickname-3qrd77 headerTag-3GFl76 nameTag-m8r81H">
                  <span class="username-2b1r56 headerTagUsernameNoNickname-2-Y5Ct headerTagUsernameBase-1NqrY5" :style="{ backgroundImage: gradient }">{{ username }}</span>
                  <span class="headerTagDiscriminatorNoNickname-D-AYUN discrimBase-24vY8o">#0001</span>
                </div>
              </div>
            </div>
            <div class="popoutInfo-1A9dyK">
              <div class="divider-ewBQKj"></div>
              <div class="aboutMeSection-1Fw5Ia">
                <h3 class="aboutMeTitle-1IYtPE fontDisplay-1dagSA base-1x0h_U size12-3cLvbJ muted-3-7c5L uppercase-3VWUQ9">À propos de moi</h3>
                <div class="aboutMeBody-3GuvKk markup-2BOw-j clamped-IwJfxR">i like takahashi rie
                  <a class="anchor-3Z-8Bb anchorUnderlineOnHover-2ESHQB" title="https://nyri4.github.io/" href="https://nyri4.github.io/" rel="noreferrer noopener" target="_blank" role="button" tabindex="0">https://nyri4.github.io/</a>
                  Avatar : <code class="inline">pixiv.net/en/artworks/67504645</code>
                  Banner : <code class="inline">pixiv.net/en/artworks/93532088</code>
                </div>
              </div>
              <div aria-hidden="true">
                <h3 class="fakeActivityTitle-ka26mT fontDisplay-1dagSA base-1x0h_U size12-3cLvbJ muted-3-7c5L uppercase-3VWUQ9">Personnalisation de mon profil</h3>
                <div class="fakeActivityLayout-AhfPCa">
                  <div class="fakeActivityIcon-2uT519 wumpus-1nZlIc">
                    <img class="fakeActivityPencil-3yYmN6" src="../assets/activity.png" style="transform: none;">
                  </div>
                  <div class="fakeActivityContent-gUkdvL">
                    <div class="colorStandard-2KCXvj size14-e6ZScH strong-1TazCs">Profil d'utilisateur</div>
                    <div class="colorStandard-2KCXvj size14-e6ZScH">Temps écoulé&nbsp;: 
                      <span class="fakeActivityTimeValues-2zDaxa">00:20</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: 'GradientPicker',
  data() {
    return {
      username: '',
      gradient: '',
      theme: 'comfy'
    }
  },
  computed: {
    themeLink() { 
      if (this.theme == 'comfy') { return 'https://nyri4.github.io/Comfy/betterdiscord/comfy.theme.css' }
      else if (this.theme == 'lilypichu') { return 'https://nyri4.github.io/LilyPichu/lilypichu.theme.css' }
      else { return 'https://nyri4.github.io/Couve/betterdiscord/couve.theme.css' }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .content {
    padding: 20px;
    display: flex; flex-direction: column;
    background-color: var(--background-secondary);
    border-radius: 16px;
  }

  main { 
    display: flex; 
    justify-content: center;
    margin-top: 10px;
  }

  .title { display: flex; align-items: center;}
  .title h3 { margin: 0;}
  .title img { 
    width: 25px; height: 20px; 
    margin-left: 8px;
  }

  .title + h4 { color: #b9bbbe; font-weight: 500;}

  @media (max-width: 800px) {
    .choices { flex-direction: column;}
  }

  .choices { 
    display: flex;
    justify-content: space-around;
    gap: 20px;
  }

  :root input { 
    width: 100%; padding: 20px;
    background-color: var(--background-primary);
    border: none; color: white;
    outline: none; font-family: 'Montserrat';
    font-weight: bold;
    border-radius: 16px;
    box-sizing: border-box;
  }
  .choices .themes {
    display: flex; gap: 20px;
  }

  .choices img { width: 56px; border-radius: 16px;}

  h3 { margin: 0;}

  /* Discord basic css */
  .profileCustomizationSection-1-Issy { margin-top: 10px;}

  .profileBannerPreview-gaX5MP {
    position: relative;
    width: 300px;
    min-width: 300px;
    min-height: 280px;
    background-color: var(--background-floating);
    border-radius: 8px;
    overflow: hidden;
    -webkit-box-shadow: var(--elevation-high);
    box-shadow: var(--elevation-high);
    font-family: var(--font-primary);

    --font-primary: Whitney,"Helvetica Neue",Helvetica,Arial,sans-serif;
    --elevation-high: 0 8px 16px rgba(0,0,0,0.24);
    --background-modifier-accent: hsla(0,0%,100%,0.06);
    --header-secondary: #b9bbbe;
    --brand-experiment-600: hsl(235,calc(var(--saturation-factor, 1)*46.7%),44.1%);
    --text-normal: #dcddde;
    --text-link: hsl(197,calc(var(--saturation-factor, 1)*100%),47.8%);
  }

  .bannerNormal-3u-o59 {     
    border-radius: 8px 8px 0 0;
    width: 100%;
    height: 60px;
  }

  .avatarUploaderNormal-1kvMcd {
    position: absolute;
    z-index: 1;
    left: 16px; top: 16px;
  }

  .avatarUploaderInner-mAGe3e {
    width: 80px;
    height: 80px;
    border: 6px solid var(--background-floating);
    background-color: var(--background-floating);
    -webkit-box-sizing: content-box;
    box-sizing: content-box;
    border-radius: 50%;
    background-size: cover;
    background-position: 50%;
    background-repeat: no-repeat;
    position: relative;
  }

  .headerTop-3vNv-a {
    display: block;
    -ms-flex-negative: 0;
    flex-shrink: 0;
    padding: 64px 16px 16px;
    overflow: hidden;
    position: relative;
    box-sizing: border-box;
  }

  .profileBadges-ohc0Vu {
    position: absolute;
    top: 16px;
    right: 16px;
    max-width: 180px;
    -webkit-box-pack: end;
    -ms-flex-pack: end;
    justify-content: flex-end;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    margin-right: -2px;
    margin-bottom: -2px;
  }

  .headerTagNoNickname-3qrd77 {
    font-size: 20px;
    line-height: 24px;
    word-break: break-word;
    white-space: normal;
    -webkit-box-align: end;
    -ms-flex-align: end;
    align-items: flex-end;
  }

  .discrimBase-24vY8o {
    color: var(--header-secondary);
    vertical-align: top;
  }

  .headerTagDiscriminatorNoNickname-D-AYUN,
  .headerTagUsernameNoNickname-2-Y5Ct { 
    font-weight: 600;
  }

  .popoutInfo-1A9dyK {
    padding: 0 16px 16px;
  }

  .divider-ewBQKj {
    height: 1px;
    background-color: var(--background-modifier-accent);
    margin-bottom: 12px;
  }

  .aboutMeSection-1Fw5Ia {
    margin-bottom: 16px;
  }

  .aboutMeTitle-1IYtPE {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    font-weight: 700;
    margin-bottom: 8px;
  }

  .aboutMeSection-1Fw5Ia .aboutMeBody-3GuvKk {
    font-size: 14px;
    line-height: 18px;
  }

  .markup-2BOw-j {
    font-size: 1rem;
    line-height: 1.375rem;
    white-space: pre-wrap;
    white-space: break-spaces;
    word-wrap: break-word;
    -webkit-user-select: text;
    -moz-user-select: text;
    -ms-user-select: text;
    user-select: text;
    color: var(--text-normal);
    font-weight: 400;
  }

  .markup-2BOw-j a {
    color: var(--text-link);
    word-break: break-word;
    text-decoration: none;
    cursor: pointer;
  }

  .markup-2BOw-j code.inline {
    width: auto;
    height: auto;
    padding: .2em;
    margin: -.2em 0;
    border-radius: 3px;
    font-size: 85%;
    font-family: Consolas,Andale Mono WT,Andale Mono,Lucida Console,Lucida Sans Typewriter,DejaVu Sans Mono,Bitstream Vera Sans Mono,Liberation Mono,Nimbus Mono L,Monaco,Courier New,Courier,monospace;
    text-indent: 0;
    border: none;
    white-space: pre-wrap;
  }

  .base-1x0h_U.muted-3-7c5L {
    color: var(--header-secondary);
  }

  .size12-3cLvbJ {
    font-size: 12px;
    line-height: 16px;
  }

  .fakeActivityIcon-2uT519, .fakeActivityLayout-AhfPCa {
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
    margin-top: 8px;
  }

  .fakeActivityIcon-2uT519.wumpus-1nZlIc {
    background-color: var(--brand-experiment-600);
    -webkit-box-pack: center;
    -ms-flex-pack: center;
    justify-content: center;
    -webkit-box-flex: 0;
    -ms-flex: 0 0 auto;
    flex: 0 0 auto;
    width: 64px;
    height: 64px;
    border-radius: 8px;
    margin-right: 16px;
    display: flex;
    -webkit-box-align: center;
    -ms-flex-align: center;
    align-items: center;
  }

  .fakeActivityPencil-3yYmN6 {
    display: block;
    width: 48px;
    height: 48px;
  }

  .fakeActivityContent-gUkdvL {
      -webkit-box-flex: 1;
      -ms-flex: 1 1 auto;
      flex: 1 1 auto;
  }

  .colorStandard-2KCXvj {
    color: var(--text-normal);
  }

  .size14-e6ZScH {
    font-size: 14px;
    line-height: 18px;
  }

  .strong-1TazCs {
      font-weight: 600;
  }

  .uppercase-3VWUQ9 {
    text-transform: uppercase;
  }

  .headerTagUsernameBase-1NqrY5
  {
    color: transparent !important;
    background-size: 300%;
    animation: shine 10s linear infinite;
    -webkit-background-clip: text;
  }

  @keyframes shine { to { background-position: 300% center;}}
  @keyframes shine-reversed { to { background-position: -300% center;}}
</style>
