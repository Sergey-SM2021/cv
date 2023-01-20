<template>
  <section class="contacts">
    <div class="container">
      <div class="contacts__inner">
        <form v-on:submit="formSubmit" class="contacts__form form-contacts">
          <div class="form-contacts__fields">
            <input
              v-model="requestCall.name"
              placeholder="Name"
              class="form-contacts__field"
            />
            <input
              v-model="requestCall.email"
              placeholder="Email"
              class="form-contacts__field"
            />
          </div>
          <textarea
            v-model="requestCall.message"
            placeholder="Message"
            class="form-contacts__field"
          ></textarea>
          <button class="form-contacts__button" type="submit">
            Send Message
          </button>
        </form>
        <div class="contacts__info info-contacts">
          <div v-for="item of contacts" class="info-contacts__item">
            <div class="info-contacts__icon">
              <img :src="item.icon" alt="" />
            </div>
            <div class="info-contacts__content">
              <div class="info-contacts__label">{{ item.label }}</div>
              <div class="info-contacts__value">
                {{ item.value }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import icon from "@/assets/shape(2).svg";
export default {
  methods: {
    formSubmit(e) {
      e.preventDefault();
    },
  },
  data() {
    return {
      requestCall: {
        name: "",
        email: "",
        message: "",
      },
      contacts: [
        {
          icon,
          value: "3424 Layman Avenue, Fayetteville, NC",
          label: "Address",
        },
        {
          icon,
          value: "3424 Layman Avenue, Fayetteville, NC",
          label: "Phone",
        },
        {
          icon,
          value: "3424 Layman Avenue, Fayetteville, NC",
          label: "E-Mail",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
@import "../const";

.contacts {
  &__inner {
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    box-sizing: border-box;
    padding: 80px 0;
    gap: 100px;
    display: flex;
    @media (max-width: 1000px) {
      gap: 60px;
    }
    @media (max-width: $mobile) {
      flex-direction: column-reverse;
      align-items: flex-start;
    }
  }
}

.form-contacts {
  width: 100%;
  flex: 1 1 55%;
  display: grid;
  &__fields {
    gap: 16px;
    display: grid;
    margin-bottom: 24px;
  }
  &__field {
    font-family: "Inter";
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 17px;
    border: none;
    box-sizing: border-box;
    padding: 16px 24px;
    color: $black;
    min-height: 48px;
    border-radius: 8px;
    outline: none;
  }
  &__button {
    &:hover {
      transform: translateX(10px);
      background-color: rgba(#7e74f1, 0.9);
      cursor: pointer;
    }
    transition: 0.25s;
    font-family: "Inter";
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 17px;
    border: none;
    border-radius: 8px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 50px;
    color: #fff;
    background-color: $purple;
  }
}

.info-contacts {
  display: grid;
  gap: 48px;
  &__item {
    display: flex;
    gap: 25px;
    align-items: center;
  }
  &__icon {
    display: flex;
    justify-content: center;
    align-items: center;
    min-width: 56px;
    height: 56px;
    border-radius: 10px;
    background-color: rgba(#7e74f1, 0.1);
  }
  &__label {
    color: $black;
    font-family: "Inter";
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 19px;
  }
  &__value {
    color: $gray;
    font-family: "Inter";
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 24px;
  }
  &__content {
    display: grid;
    align-content: space-around;
    height: 100%;
  }
}

textarea.form-contacts__field {
  height: 189px;
  width: 100%;
  margin-bottom: 48px;
}
</style>
