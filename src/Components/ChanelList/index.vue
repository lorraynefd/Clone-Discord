<template>
  <div class="container">
    <div class="category">
      <div class="">Canais de Textos</div>
      <div class="category-icons">+</div>
    </div>
    <ChanelButton selected chanelName="chat-livre" />
    <ChanelButton chanelName="jogos" />
    <ChanelButton chanelName="trabalho" />
    <ChanelButton chanelName="facul" />
    <ChanelButton chanelName="curso" />
  </div>
</template>

<script>
import ChanelButton from "./ChanelButton";
export default {
  components: {
    ChanelButton,
  },
};
</script>

<style lang="scss" scoped>
.container {
  grid-area: CL;
  display: flex;
  flex-direction: column;
  padding: 24px 10px 0 16px;
  background-color: var(--secondary);
}
.category {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 6px;
  color: var(--grey);
  font-size: 12px;
  font-weight: 500;
  text-transform: uppercase;
  .category-icons {
    color: var(--symbol);
    cursor: pointer;
    font-size: 21px;
  }
}
</style>