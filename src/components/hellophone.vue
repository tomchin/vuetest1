<template>
  <div class="css-flex">
    <mt-button type="primary" @click="handleClick1">Button 1</mt-button>
    <mt-button plain @click="handleClick2">Button 2</mt-button>
  </div>
</template>

<script>
import Vue from 'vue';
import MintUI from 'mint-ui';
import 'mint-ui/lib/style.css'
Vue.use(MintUI)

export default {
  data() {
    return {};
  },
  methods: {
    handleClick1: function() {
      MintUI.Toast("Hello world!");
    },
    handleClick2: function() {
      MintUI.MessageBox('MessageBox', "Hello world!");
    }
  }
};
</script>

<style scoped>
.css-flex {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>

