<template>
  <div class="css-flex">
    <mt-button type="primary" @click="handleClick1">Button 1</mt-button>
    <input v-model="in_msg" placeholder="edit me">
    <mt-button plain @click="handleClick2">Button 2</mt-button>
    <textarea v-model="msg_out" rows="20" cols="30"></textarea>
  </div>
</template>

<script>
import Vue from "vue";
import MintUI from "mint-ui";
import "mint-ui/lib/style.css";
Vue.use(MintUI);

import { Plugins } from "@capacitor/core";

export default {
  data() {
    return {
      in_msg: "",
      msg_out: "",
    };
  },
  methods: {
    handleClick1: function() {
      MintUI.Toast("MintUI.Toast");
    },
    async handleClick2() {
      this.msg_out += this.in_msg + "\n";
      await Plugins.Toast.show({
        text: "Native Toast"
      });
    }
  }
};
</script>

<style scoped>
.css-flex {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 600px;
}
</style>

