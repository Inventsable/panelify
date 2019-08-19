<template>
  <!-- <div class="fake-panel-bg"> -->
  <div class="fake-panel-wrapper">
    <div class="fake-panel-header">
      <div class="fake-panel-tab">
        <div class="fake-panel-title">{{extName}}</div>
        <div class="fake-panel-menu">
          <hamburger />
        </div>
      </div>
    </div>
    <div class="fake-panel-content">
      <slot></slot>
    </div>
  </div>
  <!-- </div> -->
</template>

<script>
import hamburger from "./hamburger.vue";

export default {
  name: "panelify",
  props: {
    extName: String,
    appName: String,
    theme: String,
    src: String,
  },
  components: {
    hamburger
  }
};
</script>

<style>
.fake-panel-bg {
  background-color: #fff;

  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.fake-panel-wrapper {
  box-sizing: border-box;
  width: 400px;
  height: 400px;
  border: 4px solid #161616;
  background-color: var(--color-bg);
  position: absolute;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: center;
  top: 0px;
  left: 0px;
}

.fake-panel-title {
  font-family: "Open Sans";
  font-size: 12px;
  user-select: none;
  cursor: default;
  color: var(--color-btn-pill-border);
}

.fake-panel-tab {
  box-sizing: border-box;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  border-style: solid;
  border-width: 0px 0px 2px 0px;
  border-color: var(--color-btn-pill-border);
}

.fake-panel-menu {
  padding-left: 8px;
  padding-top: 6px;
  width: 14px;
}

.fake-panel-header {
  color: var(--color-default);
  align-items: center;
  width: auto;
  padding-left: 10px;
  display: flex;
  flex-wrap: nowrap;
  box-sizing: border-box;
  height: 30px;
  background-color: #232323;
  border-style: solid;
  border-width: 0px 0px 2px 0px;
  border-color: #292929;
}
.fake-panel-content {
  box-sizing: border-box;
  height: calc(100% - 30px);
  width: 100%;
}
</style>