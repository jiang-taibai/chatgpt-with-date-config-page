<script setup>
import {defineProps} from 'vue';
import {NScrollbar} from 'naive-ui';

const props = defineProps({
  dark: {
    type: Boolean,
    default: false,
  },
  dialogue: {
    type: Array,
    default: () => [],
  },
});

import Message from "./Message.vue";
</script>

<template>
  <div :class="{
    container: true,
    dark: props.dark,
  }">
    <n-scrollbar style="max-height: 100vh">
      <div class="messages">
        <message :dark="props.dark" v-for="message in props.dialogue" :key="message.id"
                 :content="message.content" :chatgpt="message.chatgpt" :data-message-id="message.dataMessageId"/>
      </div>
    </n-scrollbar>
  </div>
</template>

<style scoped lang="less">
.container {
  background-color: #FFFFFF;
  color: #000000;
  padding: 0 20px;

  .messages {
    padding: 20px 0;
    display: grid;
    justify-content: center;
    gap: 20px;
  }
}

.container.dark {
  background-color: #212121;
  color: #fff;
}
</style>