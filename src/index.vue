<template>
  <wxc-tab-bar :tab-titles="tabTitles" :tab-styles="tabStyles" title-type="icon" @wxcTabBarCurrentTabSelected="wxcTabBarCurrentTabSelected">
    <!--The first page content-->
    <div class="item-container" :style="contentStyle">
      <div style="align-items:center">
<div class="wrapper">
  <web class="webview" src="http://ubuntu.curtasoft.org/game/plane/"></web>
</div>
</div>
</div>

<!--The second page content-->
<div class="item-container" :style="contentStyle">
  <div style="align-items:center">
<div class="wrapper">
  <web class="webview" src="http://ubuntu.curtasoft.org/game/defence/"></web>
</div>
</div>
</div>

<!-- The third page content-->
<div class="item-container" :style="contentStyle">
  <div style="align-items:center">
<div class="wrapper">
  <web class="webview" src="http://www.baidu.com"></web>
</div>
</div>
</div>

<!-- The fourth page content-->
<div class="item-container" :style="contentStyle">
  <div style="align-items:center">
<div class="wrapper">
  <web class="webview" src="http://www.egret.com"></web>
</div>
</div>

</div>
</wxc-tab-bar>
</template>

<style scoped>
.item-container {
  width: 750px;
  height: 930px;
  background-color: #f2f3f4;
  align-items: center;
  justify-content: center;
}
.wrapper {
  width: 704px;
  height: 930px;
  border-width: 2px;
  border-style: solid;
  border-color: #ccc;
  box-shadow: '2px 2px 2px #bbb'
}
.webview {
  width: 700px;
  height: 930px;
}
</style>
<script>
  import { WxcTabBar, Utils } from "weex-ui";

  // https://github.com/alibaba/weex-ui/blob/master/example/tab-bar/config.js
  import Config from "./config";

  export default {
    components: { WxcTabBar },
    data: () => ({
      tabTitles: Config.tabTitles,
      tabStyles: Config.tabStyles
    }),
    created() {
      const tabPageHeight = Utils.env.getPageHeight();
      // If the page doesn't have a navigation bar
      // const tabPageHeight = env.deviceHeight / env.deviceWidth * 750;
      const { tabStyles } = this;
      this.contentStyle = { height: tabPageHeight - tabStyles.height + "px" };
    },
    methods: {
      wxcTabBarCurrentTabSelected(e) {
        const index = e.page;
        // console.log(index);
      }
    }
  };
</script>