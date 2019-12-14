<template>
  <div id="app">
    <h1>아코디언</h1>
    <accordion title="hello">
      <p>Lorem ipsum dolor sit amet, ut alii voluptaria est, ad illum inimicus deterruisset eam. His eu bonorum adipisci definiebas, no vis nostrud conclusionemque. Ad his virtute accusata, pro habemus singulis temporibus ut, ne bonorum dolores euripidis quo. No nam amet erant intellegebat. Rationibus instructior id pri, vis case abhorreant ea, id sea meis feugiat.</p>
    </accordion>
    <accordion title="example1">
      <p>Lorem ipsum dolor sit amet, ut alii voluptaria est, ad illum inimicus deterruisset eam. His eu bonorum adipisci definiebas, no vis nostrud conclusionemque. Ad his virtute accusata, pro habemus singulis temporibus ut, ne bonorum dolores euripidis quo. No nam amet erant intellegebat. Rationibus instructior id pri, vis case abhorreant ea, id sea meis feugiat.</p>
      <hr>
      <p>Lorem ipsum dolor sit amet, ut alii voluptaria est, ad illum inimicus deterruisset eam. His eu bonorum adipisci definiebas, no vis nostrud conclusionemque. Ad his virtute accusata, pro habemus singulis temporibus ut, ne bonorum dolores euripidis quo. No nam amet erant intellegebat. Rationibus instructior id pri, vis case abhorreant ea, id sea meis feugiat.</p>
    </accordion>
    <h1>셀렉트</h1>
    <customSelect :selectData="category">
        <template slot="customSelectList" slot-scope="props">
          <template v-for="(item, idx) in category">
            <button type="button" @click="props.clickList(item)" :key="`select-item-${idx}`">
              <span>
                <b>(무료)</b> {{ item }} <strong> 좋아요</strong>
              </span>
            </button>
          </template>
        </template>
    </customSelect>
  </div>
</template>

<script>
import customSelect from './components/select'
import Accordion from './components/accordion'

export default {
  name: 'App',
  components: {
    Accordion,
    customSelect
  },
  data () {
    return {
      category: ['hello', 'hi', 'how r u?', 'im fine']
    }
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
