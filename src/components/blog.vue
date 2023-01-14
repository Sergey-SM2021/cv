<template>
  <section class="blog">
    <div class="container">
      <div class="blog__inner">
        <app-title
          class="blog__title"
          value="Personal Blog"
          label="MY ARTICLES"
        />
        <div class="blog__items">
          <div v-for="item in items" class="blog__item item-blog">
            <div class="item-blog__media">
              <img :src="item.media" />
            </div>
            <div class="item-blog__content">
              <div class="item-blog__body">
                <div class="item-blog__title">{{ item.title }}</div>
                <div class="item-blog__date">{{ item.date }}</div>
                <div class="item-blog__description">{{ item.description }}</div>
              </div>
              <div class="item-blog__footer">
                <div class="item-blog__action">Continue Reading</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import blog1 from "@/assets/Blog1.png";
export default {
  data() {
    return {
      items: [
        {
          media: blog1,
          title: "How to prototype in figma",
          date: "July 15, 2021",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora laudantium praesentium perspiciatis voluptates officia veniam temporibus vitae omnis vero hic quaerat pariatur, sequi eos impedit tenetur provident distinctio aut quidem.",
        },
        {
          media: blog1,
          title: "How to prototype in figma",
          date: "July 15, 2021",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora laudantium praesentium perspiciatis voluptates officia veniam temporibus vitae omnis vero hic quaerat pariatur, sequi eos impedit tenetur provident distinctio aut quidem.",
        },
        {
          media: blog1,
          title: "How to prototype in figma",
          date: "July 15, 2021",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Tempora laudantium praesentium perspiciatis voluptates officia veniam temporibus vitae omnis vero hic quaerat pariatur, sequi eos impedit tenetur provident distinctio aut quidem.",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
@import "../const";
.blog {
  min-height: 100vh;
  &__inner {
    gap: 144px;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100%;
    justify-content: center;
  }
  &__items {
    width: 100%;
    display: grid;
    gap: 40px;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  }
}

.item-blog {
  width: 100%;
  border-radius: 8px;
  overflow: hidden;
  background-color: #fff;
  color: #656d72;
  flex-direction: column;
  gap: 16px;
  display: flex;
  &:hover {
    cursor: pointer;
    .item-blog__action {
      color: #fff;
      background-color: $purple;
    }
    .item-blog__media img {
      transform: scale(1.1);
    }
  }
  &__title {
    font-family: "Plus Jakarta Sans";
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    color: #232e35;
  }
  &__date {
    font-family: "Inter";
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 15px;
  }
  &__description {
    font-family: "Inter";
    font-style: normal;
    font-weight: 400;
    font-size: 16px;
    line-height: 32px;
  }
  &__body {
    padding: 0 16px 0 16px;
    display: flex;
    gap: 16px;
    flex-direction: column;
  }
  &__footer {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    height: 65px;
  }
  &__action {
    padding: 24px 16px;
    transition: 1s;
  }
  &__media {
    height: 100%;
    overflow: hidden;
    max-height: 243px;
    transition: 1s;
    img {
      transition: 1s;
      object-fit: cover;
      object-position: center;
      width: 100%;
      max-width: 100%;
    }
  }
  &__content {
    height: 100%;
    border-width: 0px 1px 1px 1px;
    border-style: solid;
    border-color: #f1f1f1;
    border-radius: 0px 0px 8px 8px;
  }
}
</style>
