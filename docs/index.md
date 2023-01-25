<script setup>
  import Hero from './components/Hero.vue'
  import ArticleCard from './components/ArticleCard.vue'
  import HomeHero from './components/HomeHero.vue'

  import data from '../data.json' 
</script>
<HomeHero />

<Hero name="Anderson Vilela" subtitle="A Frontend developer (him/her) currently building with vue.js" />
<ArticleCard :data="data" />
