<template>
  <div class="wrapper">
    <app-header />
    <app-intro />
    <app-services />
    <app-portfolio />
    <app-experience />
    <app-blog />
    <app-clients />
    <app-skills />
    <app-contacts />
    <app-footer />
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
import AppSkills from "@/components/skills.vue";
import AppContacts from "@/components/contacts.vue";
import AppFooter from "@/components/footer.vue";

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
    AppSkills,
    AppContacts,
    AppFooter,
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
