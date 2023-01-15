<template>
  <section class="skills">
    <div class="container">
      <div class="skills__inner">
        <app-title value="Education & Skills" label="LEARNING PATH" />
        <div class="skills__body">
          <div class="skills__timeline timeline">
            <div class="timeline__item" v-for="item in timeline">
              <div class="timeline__title">{{ item.title }}</div>
              <div class="timeline__subtitle">
                {{ item.subtitle }}
              </div>
              <div class="timeline__date">{{ item.date }}</div>
            </div>
          </div>
          <div class="skills__content content-skills">
            <div class="content-skills__text">
              <p>
                For 5+ years, I have been continuously learning in the field of
                front-end and experimenting with new technologies and
                frameworks, and here you can see a summary of my skills.
              </p>
            </div>
            <div class="content-skills__items">
              <div class="content-skills__item">
                <div class="content-skills__label">React</div>
                <div class="content-skills__line">
                  <span style="width: 67.5%"></span>
                </div>
              </div>
              <div class="content-skills__item">
                <div class="content-skills__label">Angular</div>
                <div class="content-skills__line">
                  <span style="width: 34.6%"></span>
                </div>
              </div>
              <div class="content-skills__item">
                <div class="content-skills__label">Vue</div>
                <div class="content-skills__line">
                  <span style="width: 72.9%"></span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      timeline: [
        {
          title: "Kingston university",
          subtitle: "Master's degree - Software Engineering",
          date: "2019 - 2021",
        },
        {
          title: "Kingston university",
          subtitle: "Bachelor's degree - Computer Engineering",
          date: "2015 - 2019",
        },
        {
          title: "Kingston university",
          subtitle: "Diploma's degree - Mathematics",
          date: "2013 - 2015",
        },
      ],
      skills: [{}],
    };
  },
};
</script>
<style lang="scss">
@import "../const";

.skills {
  background-color: #fff;
  &__inner {
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100%;
    min-height: 100vh;
    gap: 100px;
  }
  &__body {
    display: grid;
    gap: 20px;
    @media (min-width: $mobile) {
      grid-template-columns: repeat(2, 1fr);
    }
  }
}

.timeline {
  position: relative;
  display: grid;
  gap: 64px;
  &::before {
    display: block;
    content: "";
    width: 1px;
    height: 100%;
    content: "";
    position: absolute;
    background-color: #f1f1f1;
    left: 8px;
  }
  &__item {
    padding-left: 28px;
    position: relative;
    &::before {
      z-index: 2;
      top: 2.5px;
      border-radius: 50%;
      width: 16px;
      height: 16px;
      left: 0;
      display: block;
      content: "";
      content: "";
      position: absolute;
      background-color: #f1f1f1;
    }
    &:last-child {
      &::after {
        inset: 0;
        right: auto;
        display: block;
        content: "";
        width: 1px;
        height: 100%;
        content: "";
        position: absolute;
        background-color: #fff;
        left: 8px;
      }
    }
  }
  &__title {
    margin-bottom: 10px;
    color: #232e35;
    font-family: "Plus Jakarta Sans";
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
  }
  &__subtitle {
    font-family: "Inter";
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 17px;
    margin-bottom: 24px;
    color: #656d72;
  }
  &__date {
    color: #232e35;
    font-family: "Inter";
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 17px;
  }
}

.content-skills {
  &__text {
    margin-bottom: 64px;
    font-family: "Inter";
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 32px;
    color: #656d72;
  }
  &__items {
    display: grid;
    gap: 40px;
  }
  &__label {
    margin-bottom: 16px;
  }
  &__line {
    background: #f5f3fe;
    border-radius: 2px;
    width: 100%;
    height: 8px;
    overflow: hidden;
    position: relative;
    span {
      position: absolute;
      inset: 0;
      background-color: $purple;
    }
  }
}
</style>
