<template>
  <div class="wrapper">
    <app-header />
    <app-intro />
    <app-services />
    <app-portfolio />
    <app-experience />
    <app-blog />
    <app-clients />
  </div>
</template>
<script>
import AppHeader from "@/components/header.vue";
import AppTitle from "@/components/title.vue";
import AppIntro from "@/components/intro.vue";
import AppServices from "@/components/services.vue";
import AppPortfolio from "@/components/portfolio.vue";
import AppExperience from "@/components/experience.vue";
import AppBlog from "@/components/blog.vue";
import AppClients from "@/components/clients.vue";

export default {
  components: {
    AppIntro,
    AppHeader,
    AppTitle,
    AppServices,
    AppPortfolio,
    AppExperience,
    AppBlog,
    AppClients,
  },
};
</script>

<style lang="scss">
@import "_const.scss";

body,
html {
  background-color: #fbfbfb;
  margin: 0;
  padding: 0;
}

li,
ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

a {
  text-decoration: none;
  color: inherit;
}
</style>
