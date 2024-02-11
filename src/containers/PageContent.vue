<template>
  <div :class="$style['page-content']">
    <slot />
  </div>
</template>
<style lang="scss" module>
.page-content {
  height: 100dvh;
  padding-left: 80px;
  overflow-y: scroll;

  @media screen and (max-width: 1100px) {
    padding-left: 0;
  }
}
</style>
