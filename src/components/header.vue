<template>
  <div class="header">
    <div class="container">
      <div class="header__inner">
        <a class="header__logo" href="#">
          <img src="@/assets/Logo.svg" alt="logo" />
        </a>
        <div class="header__menu menu">
          <transition name="fade">
            <nav v-if="isModalOpen" class="menu__body">
              <ul class="menu__list">
                <li class="menu__item">
                  <a href="#services">Services</a>
                </li>
                <li class="menu__item">
                  <a href="#portfolios">Portfolios</a>
                </li>
                <li class="menu__item">
                  <a href="#experience">Experience</a>
                </li>
                <li class="menu__item">
                  <a href="#blog">Blog</a>
                </li>
              </ul>
            </nav>
          </transition>
        </div>
        <div class="header__actions">
          <transition name="bg">
            <button @click="resumeclick" class="header__button">Resume</button>
          </transition>
          <app-burger
            :isOpen="isModalOpen"
            @changeModalVisible="changeModalVisible"
          ></app-burger>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import AppBurger from "@/components/burger.vue";

export default {
  components: {
    AppBurger,
  },
  data() {
    return {
      isModalOpen: true,
    };
  },
  methods: {
    changeModalVisible() {
      this.isModalOpen = !this.isModalOpen;
    },
    resumeclick() {
      console.log(`hi`);
    },
  },
};
</script>
<style lang="scss">
@import "../const";
.container {
  margin: 0 auto;
  max-width: 1210px;
  box-sizing: border-box;
  padding: 0 15px;
  height: 100%;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.bg-enter-active,
.bg-leave-active {
  transition: background-color 2s ease;
}

.header {
  background-color: rgba($color: #fff, $alpha: 0.75);
  box-sizing: border-box;
  padding: 40px 0;
  position: fixed;
  inset: 0;
  bottom: auto;
  width: 100%;
  z-index: 100;
  @media (max-width: $mobile) {
    padding: 10px 0;
  }
  &__inner {
    display: flex;
    align-items: center;
    gap: 15px;
  }
  &__button {
    &:hover {
      cursor: pointer;
      background-color: $purple;
    }
    transition: background-color 0.5s ease;
    padding: 16px 24px;
    background-color: transparent;
    border: solid 1px #f1f1f1;
    border-radius: 10px;
    color: $black;
    font-size: 14px;
  }
  &__logo {
    position: relative;
    z-index: 100;
  }
  &__actions {
    @media (max-width: $mobile) {
      gap: 50px;
      align-items: center;
      display: flex;
    }
    @media (max-width: $mobile-small) {
      gap: 15px;
    }
  }
}

.menu {
  width: 100%;
  &__list {
    gap: 56px;
    display: flex;
    @media (max-width: $mobile) {
      flex-direction: column;
      width: 100%;
      align-items: center;
    }
  }
  &__body {
    display: flex;
    justify-content: center;
    flex: 1 1 auto;
    @media (max-width: $mobile) {
      padding-top: 150px;
      inset: 0;
      position: fixed;
      z-index: 10;
      background-color: #7e74f1;
    }
  }
  &__item {
    color: $black;
    transition: background-color 0.5s ease;
    &:hover {
      color: $purple;
    }
    @media (max-width: $mobile) {
      font-size: 40px;
      font-weight: 600;
      color: #fff;
      &:hover {
        color: #fff;
      }
    }
  }
}
</style>
