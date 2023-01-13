<template>
  <div @click="handleclick" class="burger">
    <span></span>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: {
      required: true,
      type: Boolean,
    },
  },
  methods: {
    handleclick() {
      this.$emit("changeModalVisible");
    },
  },
};
</script>

<style lang="scss">
@import "../const";

.burger {
  @media (max-width: $mobile) {
    position: relative;
    z-index: 1000;
    width: 30px;
    height: 20px;
    display: flex;
    align-items: center;
    &::after {
      bottom: 0;
      width: 100%;
      height: 2px;
      position: absolute;
      display: block;
      background-color: #232e35;
      content: "";
    }
    &::before {
      top: 0;
      width: 100%;
      height: 2px;
      position: absolute;
      display: block;
      background-color: #232e35;
      content: "";
    }
    span {
      width: 100%;
      height: 2px;
      display: block;
      background-color: #232e35;
    }
  }
}
</style>
