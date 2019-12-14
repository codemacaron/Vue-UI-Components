<template>
  <div class="custom-select">
    <label for="customSelect" v-show="inputValue === ''"> 선택 </label>
    <div class="custom-select-input">
      <input id="customSelect" type="text" readonly :value="inputValue" @click="isSelectOpen()">
      <button type="button" @click="isSelectOpen()" :class="isOpen ? 'active' : ''"></button>
    </div>
    <ul class="custom-select-lists" v-show="isOpen">
      <slot name="customSelectList" :clickList="clickList">
        <li v-for="(list, i) in selectData" :key="i">
          <button type="button" @click="clickList(list)">
            <span> {{ list }} </span>
          </button>
        </li>
      </slot>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'customSelect',
  props: {
    selectData: {
      type: Array,
      default: function () {
        return []
      }
    }
  },
  data () {
    return {
      inputValue: '',
      isOpen: false
    }
  },
  methods: {
    isSelectOpen () {
      if (this.isOpen === false) {
        this.isOpen = true
      } else {
        this.isOpen = false
      }
    },
    clickList (props) {
      this.inputValue = props
      this.isOpen = false
    }
  }
}
</script>

<style lang="scss">
.custom-select {
  position: relative;
  text-align: left;
  border: 1px solid #ccc;
  padding: 0;
  width: 300px;
  box-sizing: border-box;
  background: #fff;
  label, input, li button{
    box-sizing: border-box;
    font-size: 13px;
    line-height: 25px;
    padding: 0 10px;
  }
  label {
    position: absolute;
    left: 0;
    top: 0;
    height: 25px;
  }
  input{
    position: relative;
    width: 100%;
    height: 25px;
    border: 0 none;
    background: inherit;
  }
}
.custom-select-input {
  display: flex;
  justify-content: space-between;
  button{
    color: #000;
    font-size: 13px;
    border: 0 none;
    background: inherit;
    width: 25px;
    height: 25px;
    line-height: 25px;
    background: url(./../assets/img/down.svg) center center no-repeat;
    background-size: 10px;
    &.active {
      background: url(./../assets/img/up.svg) center center no-repeat;
      background-size: 10px;
    }
  }
}
.custom-select-lists {
  position: absolute;
  left: -1px;
  top: 25px;
  width: 300px;
  background: #fff;
  border: 1px solid #ccc;
  box-sizing: border-box;
  button {
    width: 100%;
    border: 0 none;
    background: inherit;
    text-align: left;
    &:hover {
      color: #14a866;
      background: rgba(#ccc, 0.2);
    }
  }
}
</style>
