<template>
  <div id="app">
    <accordion title="hello">
      <p>Lorem ipsum dolor sit amet, ut alii voluptaria est, ad illum inimicus deterruisset eam. His eu bonorum adipisci definiebas, no vis nostrud conclusionemque. Ad his virtute accusata, pro habemus singulis temporibus ut, ne bonorum dolores euripidis quo. No nam amet erant intellegebat. Rationibus instructior id pri, vis case abhorreant ea, id sea meis feugiat.</p>
    </accordion>
    <accordion title="example1">
      <p>Lorem ipsum dolor sit amet, ut alii voluptaria est, ad illum inimicus deterruisset eam. His eu bonorum adipisci definiebas, no vis nostrud conclusionemque. Ad his virtute accusata, pro habemus singulis temporibus ut, ne bonorum dolores euripidis quo. No nam amet erant intellegebat. Rationibus instructior id pri, vis case abhorreant ea, id sea meis feugiat.</p>
      <hr>
      <p>Lorem ipsum dolor sit amet, ut alii voluptaria est, ad illum inimicus deterruisset eam. His eu bonorum adipisci definiebas, no vis nostrud conclusionemque. Ad his virtute accusata, pro habemus singulis temporibus ut, ne bonorum dolores euripidis quo. No nam amet erant intellegebat. Rationibus instructior id pri, vis case abhorreant ea, id sea meis feugiat.</p>
    </accordion>
  </div>
</template>

<script>
import Accordion from './components/accordion'

export default {
  name: 'App',
  components: {
    Accordion
  }
}
</script>

<style lang="scss">
  @import './sass/App';
  @font-face {
    font-family: 'Nanum Square';
    src: url('./assets/font/NanumSquareR.eot');
    src: url('./assets/font/NanumSquareR.eot?#iefix') format('embedded-opentype'), url('./assets/font/NanumSquareR.woff') format('woff'), url('./assets/font/NanumSquareR.ttf') format('truetype'), url('./assets/font/NanumSquareOTFR.svg#9e23ceb0c858ca37642ba540402577eb') format('svg');
    font-style: normal;
    font-weight: 400;
  }

  @font-face {
    font-family: 'Nanum Square';
    src: url('./assets/font/NanumSquareB.eot');
    src: url('./assets/font/NanumSquareB.eot?#iefix') format('embedded-opentype'), url('./assets/font/NanumSquareB.woff') format('woff'), url('./assets/font/NanumSquareB.ttf') format('truetype'), url('./assets/font/NanumSquareOTFB.svg#a41a1fda1fdf3dafd3394867a156b1cf') format('svg');
    font-style: normal;
    font-weight: 700;
  }

  #app {
    font-family: 'Nanum Square', 'Avenir', Helvetica, Arial, sans-serif;
    text-align: left;
    color: #000;
  }
</style>
