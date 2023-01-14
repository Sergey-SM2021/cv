<script>
import crown from "@/assets/crown.svg";
import icon from "@/assets/Icon.svg";
import shape from "@/assets/shape.svg";

export default {
  data() {
    return {
      articles: [
        {
          icon: crown,
          title: "UI/UX Design",
          text: "Turn what you have in mind of a digital product into reality. For any platform you consider.",
        },
        {
          icon: icon,
          title: "Application Development",
          text: "Standard designing, building, and implementing your applications with documentation.",
        },
        {
          icon: shape,
          title: "Web Development",
          text: "Create and maintain your websites and also take care of its performance and traffic capacity.",
        },
      ],
    };
  },
};
</script>
<template>
  <section class="servises">
    <div class="container">
      <div class="servises__content">
        <app-title
          class="servises__title"
          label="SERVICES"
          value="Specialized in"
        />
        <div class="servises__articles">
          <div
            class="servises__article article-servises"
            v-for="article of articles"
          >
            <div class="article-servises__icon">
              <img :src="article.icon" />
            </div>
            <div class="article-servises__title">{{ article.title }}</div>
            <div class="article-servises__text">{{ article.text }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<style lang="scss">
@import "../const";
.servises {
  height: 100vh;
  &__articles {
    display: grid;
    gap: 50px;
    grid-template-columns: repeat(auto-fit, minmax(301px, 1fr));
    @media (max-width: $mobile) {
      gap: 30px;
    }
  }
  &__title {
    margin-bottom: 50px;
  }
  &__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100%;
  }
  &__articles {
    width: 100%;
  }
}

.article-servises {
  &:hover {
    transform: translateY(-10px);
    cursor: pointer;
  }
  transition: all .3s;
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  border-radius: 10px;
  box-sizing: border-box;
  padding: 50px;
  background-color: #fff;
  &__title {
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    margin-bottom: 16px;
  }
  &__text {
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 24px;
  }
  &__icon {
    margin-bottom: 24px;
  }
}
</style>
