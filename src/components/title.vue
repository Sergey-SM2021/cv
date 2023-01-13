<template>
  <div class="title">
    <div class="title__label">{{ label }}</div>
    <div class="title__value">{{ value }}</div>
  </div>
</template>

<style lang="scss">
@import "../const";
.title {
  display: flex;
  flex-direction: column;
  gap: 8px;
  @media (max-width: $mobile) {
    gap: 0px;
  }
  &__label {
    padding-left: 32px;
    position: relative;
    font-size: 12px;
    font-weight: 500;
    color: $gray;
    letter-spacing: 7.5px;
    line-height: 24px;
    &::before {
      left: 0;
      background-color: $gray-light;
      height: 2px;
      width: 16px;
      content: "";
      top: 50%;
      position: absolute;
      display: block;
      transform: translateY(-50%);
    }
  }
  &__value {
    font-size: 36px;
    font-weight: bold;
    color: $black;
  }
}
</style>

<script>
export default {
  props: {
    label: String,
    value: String,
  },
};
</script>
