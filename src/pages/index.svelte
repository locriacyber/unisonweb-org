<script context="module">
  import pageContent from "../data/pages/index.yml";
  import Hero from "../components/Hero";
  import HeroGraphic from "../components/Homepage/HeroGraphic";
  import Links from "../components/Homepage/Links";
  import pageMetaInfo from "../mixins/pageMetaInfo";
</script>

<script>
  $: pageContent = pageContent;
</script>

<template lang="pug">

un-site-main
  un-hero(eyebrow='{pageContent.hero.eyebrow}' heading='{pageContent.hero.heading}' blurb='{pageContent.hero.blurb}' cta='{pageContent.hero.cta}' graphic='{pageContent.hero.graphic}')
    un-hero-graphic(graphic='{pageContent.hero.graphic}').
      
      
  un-page-section(size='large')
    .container
      .row.center-xs.u-align--left
        .col-xs-12.col-sm-10.col-md-12
          vue-markdown.sb-homepage-intro.u-drop-cap(source='{pageContent.intro}').
            
            
  un-page-section.u-bg--gray--xxx-light(size='large')
    .container.u-align--center@xs.u-align--center@sm
      un-homepage-links(heading='{pageContent.links.heading}' items='{pageContent.links.items}' button='{pageContent.links.button}').
</template>

<style lang="scss">
  :global(.sb-homepage-intro) {
    font-family: font(light);
    letter-spacing: dim(letterSpacing, -2);
    > p {
      &:first-of-type {
        font-size: rem(2);
        letter-spacing: dim(letterSpacing, -3);
      }
    }
  }
</style>
