<template>
  <div class="title">
    <div class="title-box">
      {{ title }}
    </div>
  </div>
</template>

<script>
export default {
  props: ["title"]
};
</script>

<style lang="scss">
$themeColor: #1acabd;
.title {
    width: 100%;
    border-bottom: 3px solid $themeColor;
    margin-bottom: 10px;
}
.title-box {
  width: 200px;
  height: 40px;
  line-height: 40px;
  background: $themeColor;
  position: relative;
  color: #fff;
  padding: 0 0 0 10px;
  font-size: 20px;
  font-weight: 700;
  &::after {
    content: "";
    width: 0;
    height: 0;
    border-bottom: 40px solid transparent;
    border-right: 40px solid #fff;
    position: absolute;
    right: 0;
  }
}
</style>
