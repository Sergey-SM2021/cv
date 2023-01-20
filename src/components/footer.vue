<template>
  <section class="footer">
    <div class="container">
      <div class="footer__inner">
        <div class="footer__items">
          <div class="footer__item">
            <img src="@/assets/twitter.svg" />
          </div>
          <div class="footer__item">
            <img src="@/assets/twitter.svg" />
          </div>
          <div class="footer__item">
            <img src="@/assets/twitter.svg" />
          </div>
          <div class="footer__item">
            <img src="@/assets/twitter.svg" />
          </div>
        </div>
        <div class="footer__copyright">© 2022 - DevChapter</div>
      </div>
    </div>
  </section>
</template>
<script>
export default {};
</script>
<style lang="scss">
.footer {
  &__inner {
    height: 240px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  &__items {
    margin-bottom: 24px;
    gap: 30px;
    justify-content: center;
    display: flex;
    width: 100%;
  }
  &__copyright {
    font-family: "Inter";
    font-style: normal;
    font-weight: 400;
    font-size: 14px;
    line-height: 17px;
    color: #656d72;
  }
}
</style>
