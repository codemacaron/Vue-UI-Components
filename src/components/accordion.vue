<template>
  <div class="cover">
    <h1 class="accordion-title">
      <span class="down-Arrow" v-show="!active">&#9660;</span>
      <span class="up-Arrow" v-show="active">&#9650;</span>
      <button type="button" @click.prevent="toggle">{{title}}</button>
    </h1>
    <transition
      @enter="startTransition"
      @after-enter="startTransition"
      @before-leave="startTransition"
      @after-leave="endTransition"
    >
      <div class="content" v-show="active">
        <slot />
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'accordion',
  props: [
    'title'
  ],
  data () {
    return {
      active: false
    }
  },

  methods: {
    toggle (event) {
      this.active = !this.active
    },

    startTransition (el) {
      console.log('startTransition :::', el.scrollHeight + 'px')
      el.style.height = el.scrollHeight + 'px'
    },

    endTransition (el) {
      console.log('endTransition :::', el.scrollHeight + 'px')
      el.style.height = ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.cover{
  position: relative;
  width: 500px;
  border-radius: 4px;
  background: lightcyan;
  h1.accordion-title{
    width: 100%;
    border-bottom: 1px solid #dedfdf;
    padding: 20px;
    box-sizing: border-box;
    span {
      display: inline-block;
    }
    button{
      display: inline-block;
      background: none;
      border: 0 none;
    }
  }
  .content{
    background: lightgray;
    padding: 20px;
    box-sizing: border-box;
  }
}

.accordion-leave,
.accordion-enter-to{
  height: auto;
}

.accordion-enter-active,
.accordion-leave-active {
  transition: all 5s ease;
}
.accordion-enter,
.accordion-leave-to {
  height: 0;
}

</style>
