<style lang="scss">
.clients {
  &__inner {
    padding: 80px 0;
    min-height: 100vh;
    height: 100%;
    display: grid;
    grid-template-rows: auto auto;
    align-items: center;
    align-content: center;
    gap: 132px;
  }
  &__items {
    gap: 48px;
    width: 100%;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(290px, 1fr));
    row-gap: 100px;
  }
  &__title {
    justify-self: start;
  }
}

.item-client {
  box-sizing: border-box;
  padding: 0 32px 32px 32px;
  justify-items: center;
  display: grid;
  background: #ffffff;
  border-radius: 8px;
  grid-template-rows: auto 1fr repeat(2, auto);
  &__ava {
    height: 96px;
    width: 96px;
    img {
      transform: translateY(-50%);
    }
  }
  &__name {
    justify-self: start;
    font-family: "Plus Jakarta Sans";
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 18px;
    color: #232e35;
    margin-bottom: 9px;
  }
  &__pofession {
    padding: 4px 8px;
    justify-self: start;
    font-family: "Inter";
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 15px;
    color: #656d72;
  }
  &__text {
    margin-bottom: 30px;
    font-weight: 400;
    font-size: 16px;
    line-height: 28px;
    color: #232e35;
  }
}
</style>
<template>
  <div class="clients">
    <div class="container">
      <div class="clients__inner">
        <app-title
          class="clients__title"
          label="MY CLIENTS"
          value="Testimonials"
        />
        <div class="clients__items">
          <div v-for="item in clients" class="client__item item-client">
            <div class="item-client__ava">
              <img :src="item.avatar" alt="" />
            </div>
            <div class="item-client__text">{{ item.text }}</div>
            <div class="item-client__name">{{ item.clientName }}</div>
            <div class="item-client__pofession">
              {{ item.clientProfession }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Client_01 from "@/assets/Avatar.png";

export default {
  data() {
    return {
      clients: [
        {
          avatar: Client_01,
          text: "We were very pleased to hear how you resolved our website's user interface issues and challenges.",
          clientName: "Amelia Miller",
          clientProfession: "Designer",
        },
        {
          avatar: Client_01,
          text: "We were very pleased to hear how you resolved our website'seased to hear how you resolved our website's user interface issues and challenges user interface issues and challengesyou resolved our website's user interface issues and challenges user interface issues and challenges.",
          clientName: "Amelia Miller",
          clientProfession: "Designer",
        },
        {
          avatar: Client_01,
          text: "We were very pleased to hear how you resolved our website's user interface issues and challenges.",
          clientName: "Amelia Miller",
          clientProfession: "Designer",
        },
      ],
    };
  },
};
</script>
