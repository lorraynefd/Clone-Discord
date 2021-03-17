<template>
  <div class="chanel-list" :class="{ active: selected }">
    <div class="chanel-info">
      <HashTagIcon class="hash-actions" :size="20" />
      <div>{{ chanelName }}</div>
    </div>
    <div class="chanel-actions">
      <InviteIcon class="icon-actions" :size="16" />
      <SettingsIcon class="icon-actions" :size="16" />
    </div>
  </div>
</template>

<script>
import HashTagIcon from "vue-material-design-icons/Pound";
import InviteIcon from "vue-material-design-icons/AccountPlus";
import SettingsIcon from "vue-material-design-icons/CogOffOutline";
export default {
  components: {
    HashTagIcon,
    InviteIcon,
    SettingsIcon,
  },
  props: {
    chanelName: String,
    selected: Boolean,
  },
};
</script>

<style lang="scss" scoped>
.chanel-list {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  cursor: pointer;
  padding: 5px 3px;
  border-radius: 5px;
  background-color: transparent;

  > div {
    display: flex;
    align-items: center;
  }
  .chanel-info {
    div {
      color: var(--senary);
      margin-left: 5px;
    }
    .hash-actions {
      color: var(--symbol);
    }
  }
  .chanel-actions {
    display: none;
    .icon-actions {
      color: var(--symbol);
      margin-left: 4px;
      transition: 0.2s;
      &:hover {
        color: var(--white);
      }
    }
  }
  &:hover,
  &.active {
    background-color: var(--quinary);
    .chanel-info {
      div {
        color: var(--white);
      }
    }
    .chanel-actions {
      display: flex;
    }
  }
}
</style>