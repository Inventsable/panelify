<template>
  <div class="block-panel-wrapper" :style="getWrapperStyle()">
    <div class="block-panel-header" :style="getHeaderStyle()">
      <div class="block-panel-tab" :style="getTabStyle()">
        <div class="block-panel-title">{{extName}}</div>
        <div class="block-panel-menu">
          <hamburger :color="getMenuColor()" />
        </div>
      </div>
    </div>
    <div class="block-panel-content">
      <iframe :src="this.src" frameborder="0" style="width: 100%; height: 100%;"></iframe>
    </div>
  </div>
</template>

<script>
import starlette from "starlette";
import hamburger from "./hamburger.vue";

export default {
  name: "panelify",
  props: {
    extName: String,
    appName: String,
    theme: String,
    width: String,
    height: String,
    gradient: Number,
    src: String
  },
  computed: {
    isBlock() {
      return /aeft|ppro|audt/i.test(this.appName);
    }
  },
  components: {
    hamburger
  },
  mounted() {
    // starlette.initAs(this.appName, this.theme);
  },
  methods: {
    getWrapperStyle() {
      return `
        width: ${this.width};
        height: ${this.height};
        border: 4px solid ${starlette.getColorAs(
          "color-header-border",
          this.appName,
          this.theme,
          this.gradient || null
        )};
        background-color: ${starlette.getColorAs(
          "color-bg",
          this.appName,
          this.theme,
          this.gradient || null
        )};
        color: ${starlette.getColorAs(
          "color-btn-pill-border",
          this.appName,
          this.theme,
          this.gradient || null
        )};
      `;
    },
    getHeaderStyle() {
      return `
        width: 100%;
        border-color: ${starlette.getColorAs(
          "color-scrollbar-thumb",
          this.appName,
          this.theme,
          this.gradient || null
        )};
      `;
    },
    getTabStyle() {
      return `
        border-color: ${starlette.getColorAs(
          "color-btn-pill-border",
          this.appName,
          this.theme,
          this.gradient || null
        )};
      `;
    },
    getMenuColor() {
      return `${starlette.getColorAs(
        "color-btn-pill-border",
        this.appName,
        this.theme,
        this.gradient || null
      )}`;
    }
  }
};
</script>

<style>
@import url(//fonts.googleapis.com/css?family=Open+Sans);

.block-panel-bg {
  background-color: #fff;

  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
}

.block-panel-wrapper {
  box-sizing: border-box;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: center;
}

.block-panel-title {
  font-family: "Open Sans";
  font-size: 12px;
  user-select: none;
  cursor: default;
}

.block-panel-tab {
  box-sizing: border-box;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  border-style: solid;
  border-width: 0px 0px 2px 0px;
}

.block-panel-menu {
  padding-left: 8px;
  padding-top: 6px;
  width: 14px;
}

.block-panel-header {
  align-items: center;
  width: 100%;
  padding-left: 10px;
  display: flex;
  flex-wrap: nowrap;
  box-sizing: border-box;
  height: 30px;
  border-style: solid;
  border-width: 0px 0px 1px 0px;
}
.block-panel-content {
  box-sizing: border-box;
  height: calc(100% - 30px);
  width: 100%;
}
</style>