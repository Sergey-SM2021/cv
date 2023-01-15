<script>
import PortfolioItem from "@/assets/Portfolio item.jpg";

export default {
  computed: {
    computedSlides() {
      if (window.innerWidth < 730) {
        return this.slides.slice(2);
      }
      if (window.innerWidth < 1000) {
        return this.slides.slice(1);
      }
      return this.slides;
    },
  },
  data() {
    return {
      slides: [
        {
          media: PortfolioItem,
          title: "Agency Website",
          skill: "WordPress",
          linkAddress: "https://www.youtube.com/watch?v=RB-RJB1siGw&t=618s",
          id: "srt13",
        },
        {
          media: PortfolioItem,
          title: "Agency Website",
          skill: "WordPress",
          linkAddress: "https://www.youtube.com/watch?v=RB-RJB1siGw&t=618s",
          id: "13265",
        },
        {
          media: PortfolioItem,
          title: "Agency Website",
          skill: "WordPress",
          linkAddress: "https://www.youtube.com/watch?v=RB-RJB1siGw&t=618s",
          id: "srt13265",
        },
      ],
    };
  },
};
</script>
<template>
  <div class="portfolio">
    <div class="container">
      <div class="portfolio__inner">
        <div class="portfolio__header">
          <app-title label="my works" value="Featured Portfolio" />
          <div class="portfolio__controlls">
            <div class="portfolio__arrow portfolio__arrow_left">
              <img src="@/assets/shape(1).svg" />
            </div>
            <div class="portfolio__arrow portfolio__arrow_right">
              <img src="@/assets/shape(1).svg" />
            </div>
          </div>
        </div>
        <div class="portfolio__slides">
          <div
            v-for="slide in computedSlides"
            class="portfolio__slide slide-portfolio"
          >
            <div class="slide-portfolio__inner">
              <div class="slide-portfolio__media">
                <img :src="slide.media" />
              </div>
              <div class="slide-portfolio__body">
                <div class="slide-portfolio__title">{{ slide.title }}</div>
                <button class="slide-portfolio__button">
                  {{ slide.skill }}
                </button>
                <a class="slide-portfolio__link" :href="slide.linkAddress">
                  <img src="@/assets/link.svg" />
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style lang="scss">
@import "../const";

.portfolio {
  &__inner {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 140px;
  }
  &__header {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  &__controlls {
    display: flex;
    gap: 16px;
  }
  &__arrow {
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 16px;
    background-color: #eae6fe;
    width: 40px;
    transition: 1s all;
    height: 40px;
    &:hover{
        cursor: pointer;
        background-color: #ddd6ff;
    }
    &_right {
    }
    &_left {
      transform: rotate(180deg);
    }
  }
  &__slides {
    gap: 20px;
    width: 100%;
    display: flex;
    justify-content: space-between;
  }
}

.slide-portfolio {
  width: 100%;
  overflow: hidden;
  border-radius: 8px;
  &:hover {
    cursor: pointer;
    .slide-portfolio__media img {
      transform: scale(1.1);
      opacity: 1;
      cursor: pointer;
    }
    .slide-portfolio__title {
      color: $purple;
    }
    .slide-portfolio__button {
      color: black;
      background-color: $purple;
    border: 1px solid $purple;
      
    }
  }
  &__inner {
    position: relative;
  }
  &__body {
    box-sizing: border-box;
    padding: 24px;
    min-height: 110px;
    background-color: #fff;
    border: 1px solid #f5f5f5;
    border-radius: 0 0 8px 8px;
    background-color: #fff;
    inset: 0;
    top: auto;
    position: absolute;
    display: flex;
    align-items: flex-start;
    flex-wrap: wrap;
    gap: 16px;
  }
  &__media img {
    opacity: 0.5;
    object-fit: cover;
    object-position: center;
    width: 100%;
    transition: all 0.7s;
  }
  &__button {
    background-color: #fff;
    border: 1px solid #f1f1f1;
    border-radius: 4px;
    padding: 4px 8px;
    transition: all 1s;
  }
  &__title {
    flex: 1 1 100%;
    transition: all 1s;
    font-weight: 500;
    font-size: 16px;
    line-height: 20px;
    color: #232e35;
  }
}
</style>
