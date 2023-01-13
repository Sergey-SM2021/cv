<style lang="scss">
@import "../const";
.intro {
  box-sizing: border-box;
  padding-top: 200px;
  height: 100vh;
  @media (max-width: $mobile) {
    padding-top: 100px;
  }
  &__inner {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    padding-right: 20px;
    @media (max-width: $mobile) {
      grid-template-columns: 1fr;
      row-gap: 30px;
      padding-left: 20px;
    }
  }
  &__content {
    display: flex;
    flex-direction: column;
  }
  &__title {
    margin-bottom: 32px;
    @media (max-width: $mobile) {
      margin-bottom: 12px;
    }
  }
  &__media {
    justify-self: end;
  }
  &__text {
    margin-bottom: 41px;
    @media (max-width: $mobile) {
      margin-bottom: 21px;
    }
  }
  &__social {
    display: flex;
    gap: 34px;
  }
}

.photo-intro {
  max-width: 336px;
  height: 400px;
  width: 100%;
  min-width: 254px;
  position: relative;
  justify-self: end;
  @media (max-width: $mobile) {
    margin: 0 auto;
  }
  &__card {
    inset: 0;
    position: absolute;
    height: 100%;
    width: 100%;
    border-radius: 10px;
  }
  &__card_pink {
    @extend .photo-intro__card;
    background-color: #eae6fe;
  }
  &__card_purple {
    transform: rotate(-10deg);
    @extend .photo-intro__card;
    background-color: $purple;
  }
  &__man {
    position: absolute;
    bottom: 0;
    left: 0;
  }
  &__liner-background {
    position: absolute;
    top: 0;
    right: 0;
  }
}

.text {
  color: $black;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 32px;
}

.container {
  margin: 0 auto;
  max-width: 1210px;
  box-sizing: border-box;
  padding: 0 15px;
}

</style>
<template>
  <section class="intro">
    <div class="container">
      <div class="intro__inner">
        <div class="intro__content">
          <app-title
            value="Alex Smith."
            label="MY NAME IS"
            class="intro__title"
          ></app-title>
          <div class="intro__text text">
            Creative front-end developer with more than +5 years of experience
            in enterprise companies and startups. Proficient in JavaScript,
            Angular, and React. Passionate about UI/UX
          </div>
          <div class="intro__social social">
            <img src="@/assets/instagram.svg" alt="" />
            <img src="@/assets/twitter.svg" alt="" />
            <img src="@/assets/github.svg" alt="" />
            <img src="@/assets/linkedin.svg" alt="" />
          </div>
        </div>
        <div class="intro__photo photo-intro">
          <div class="photo-intro__card_purple"></div>
          <div class="photo-intro__card_pink">
            <img
              src="@/assets/lines.svg"
              class="photo-intro__liner-background"
            />
            <img class="photo-intro__man" src="@/assets/sssss 1.png" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import AppTitle from "@/components/title.vue";

export default {
  components: {
    AppTitle,
  },
};
</script>
