<template>
  <div class="channeldata">
    <div class="messages">
      <ChanelMessage
        :author="generateName()"
        date="12/03/1982"
        v-for="messages in 18"
        :key="messages.id"
        >E ai. Blz..como vc esta nesse dia de sol e chuvas</ChanelMessage
      >
      <ChanelMessage
        ref="new"
        author="Maikel Neris"
        date="12/03/1982"
        isBot
        hasMention
      >
        <Mention>Lorrayne Ferreira</Mention>testando função de mensagem
      </ChanelMessage>
    </div>
    <div class="inputwrapper">
      <input type="text" placeholder="Conversar em #chat-livre" />
      <div class="icon">
        <At :size="24" />
      </div>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import ChanelMessage from "./ChanelMessage";
import At from "vue-material-design-icons/At";
import randomName from "../../data/names";
export default {
  components: {
    ChanelMessage,
    At,
  },
  methods: {
    generateName() {
      return randomName();
    },
  },
};
Vue.component("Mention", {
  template: '<span class="mention"><slot /></span>',
});
</script>

<style lang="scss" scoped>
.channeldata {
  grid-area: CD;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: var(--primary);
  flex: 1;
}
.messages {
  display: flex;
  flex-direction: column;
  height: calc(100vh - 46px - 68px);
  max-height: calc(100vh - 46px - 68px);
  overflow-y: scroll;
  .ChanelMessage:first-child {
    margin-top: 0;
  }
  &::-webkit-scrollbar {
    width: 8px;
  }
  &::-webkit-scrollbar-thumb {
    background-color: var(--tertiary);
    border-radius: 4px;
  }
  &::-webkit-scrollbar-track {
    background-color: var(--secondary);
  }
}
.inputwrapper {
  width: 100%;
  padding: 0 16px;
  height: 68px;
  input {
    width: 100%;
    height: 44px;
    padding: 0 10px 0 57px;
    border-radius: 5px;
    color: var(--white);
    background-color: var(--chat-input);
    position: relative;
    &::placeholder {
      color: var(--grey);
    }
  }
  .icon {
    color: var(--grey);
    position: relative;
    top: -50%;
    left: 14px;
    transition: ease-out all 0.2s;
    width: 24px;
  }
}
</style>