<template>
  <div id="grid">
    <ServerList />
    <ServerName />
    <ChanelInfo />
    <ChanelList />
    <UserInfo />
    <ChanelData />
    <UserList />
  </div>
</template>

<script>
import ServerList from "./ServerList";
import ServerName from "./ServerName";
import ChanelInfo from "./ChanelInfo";
import ChanelList from "./ChanelList";
import UserInfo from "./UserInfo";
import ChanelData from "./ChanelData";
import UserList from "./UserList";
export default {
  components: {
    ServerList,
    ServerName,
    ChanelInfo,
    ChanelList,
    UserInfo,
    ChanelData,
    UserList,
  },
};
</script>

<style scoped>
#grid {
  display: grid;
  grid-template-columns: 71px 240px auto 240px;
  grid-template-rows: 46px auto 52px;
  grid-template-areas:
    "SL SN CI CI"
    "SL CL CD UL"
    "SL UI CD UL";
  height: 100vh;
}
</style>