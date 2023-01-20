<template>
  <section class="experience">
    <div class="container">
      <div class="experience__inner">
        <app-title
          class="experience__title"
          label="career path"
          value="Work Experices"
        />
        <div class="experience__content content-experience">
          <div class="content-experience__title">
            {{ CompanyActive.name }}
          </div>
          <div class="content-experience__body">
            <div class="content-experience__location">
              {{ CompanyActive.location }}
            </div>
            <div class="content-experience__time">
              {{ CompanyActive.time }}
            </div>
            <ul class="content-experience__tegs">
              <li
                v-for="t in CompanyActive.tags"
                class="content-experience__teg"
              >
                {{ t }}
              </li>
            </ul>
          </div>
          <ul class="content-experience__tasks">
            <li
              v-for="skill in CompanyActive.skills"
              class="content-experience__task"
            >
              {{ skill }}
            </li>
          </ul>
        </div>
        <nav class="experience__nav nav-experience">
          <buttun
            @click="chooseCompany(item.id)"
            v-for="item in companies"
            :key="item.id"
            :class="{
              'nav-experience__item_active': item.id === CompanyAct.id,
              'nav-experience__item': true,
            }"
          >
            <div class="nav-experience__title">{{ item.name }}</div>
            <div class="nav-experience__arrow">
              <img src="@/assets/shape(1).svg" alt="" />
            </div>
          </buttun>
        </nav>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  mounted() {
    this.defaultId = Math.random().toString();
  },
  defaultId: "",
  methods: {
    chooseCompany(CompanyId) {
      this.CompanyAct.id = CompanyId;
    },
  },
  computed: {
    CompanyActive() {
      return this.companies.filter((c) => c.id === this.CompanyAct.id)[0];
    },
  },
  data() {
    return {
      CompanyAct: {
        id: this.$options.defaultId,
      },
      companies: [
        {
          name: "Apple",
          id: this.$options.defaultId,
          title: "Front-end Developer  Apple .Inc",
          location: "California, United States",
          tags: ["Swift", "Go"],
          skills: [
            "Improving overall website performance for mobile users.",
            "Collaborate with back-end developers and web designers to improve usability",
            "Add voice search feature for mobile app.",
            "Developing an admin panel to manage contents, users, products and ...",
          ],
          time: "Nov 2021 - Present · Full-time",
        },
        {
          time: "Jun 2022 - Present · Part-time",
          name: "Digital 407",
          id: Math.random().toString(),
          title: "Front-end Developer in Digital 407 company",
          location: "Батуми",
          tags: ["React", "Redux", "toolkit"],
          skills: [
            "Регистрация и авторизация по jwt",
            "Работа с react-hook-forms/formik",
            "Адаптивная вёрстка",
          ],
        },
      ],
    };
  },
};
</script>
<style lang="scss">
@import "../const";
.experience {
  height: 100vh;
  &__inner {
    height: 100%;
    display: grid;
    align-content: center;
    grid-template: auto auto / auto 1fr;
    column-gap: 144px;
    row-gap: 80px;
    @media (max-width: $mobile) {
        grid-template: auto / auto;
    }
  }
  &__tabs {
    grid-template-columns: auto 1fr;
  }
  &__content {
    grid-row: span 2;
    @media (max-width: $mobile) {
      order: 3;
    }
  }
  &__nav {
    gap: 24px;
    display: grid;
    @media (max-width: $mobile) {
      order: 2;
    }
  }
  &__title {
    @media (max-width: $mobile) {
      order: 1;
    }
  }
}

.content-experience {
  &__title {
    font-weight: 500;
    font-size: 18px;
    line-height: 23px;
    color: #232e35;
    margin-bottom: 8px;
  }
  &__body {
    display: grid;
    gap: 16px;
  }
  &__location {
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 17px;
    color: #656d72;
  }
  &__time {
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 24px;
    color: #656d72;
  }
  &__tegs {
    display: flex;
    gap: 16px;
    padding-bottom: 30px;
    border-bottom: 1px solid #f1f1f1;
  }
  &__teg {
    border: 1px solid #f1f1f1;
    padding: 4px 8px;
    border-radius: 4px;
    font-family: "Inter";
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 15px;
    color: #656d72;
    box-sizing: border-box;
    transition: 1s;
    &:hover {
      background-color: $purple;
      cursor: pointer;
      color: #fff;
    }
  }
  &__tasks {
    padding-top: 30px;
    font-family: "Inter";
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 19px;
    color: #656d72;
  }
  &__task {
    padding-left: 30px;
    margin-bottom: 16px;
    position: relative;
    &::before {
      content: "";
      width: 10px;
      height: 2px;
      background-color: #d9d9d9;
      display: block;
      position: absolute;
      inset: 0;
      right: auto;
      top: 0.5em;
      transform: translateY(50%);
    }
  }
}

.nav-experience {
  &__item {
    transition: transform 1s;
    &:hover {
      cursor: pointer;
      transform: translateX(30px);
    }
    display: flex;
    border-radius: 4px;
    background-color: #fff;
    padding: 12px 14px;
    align-items: center;
  }
  &__arrow {
    display: none;
  }
  &__item_active {
    @extend .nav-experience__item;
    .nav-experience__arrow {
      flex: 1 1 auto;
      display: flex;
      justify-content: flex-end;
    }
    color: $purple;
  }
}
</style>
