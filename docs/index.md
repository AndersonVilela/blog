<script setup>
  import Hero from './components/Hero.vue'
  import ArticleCard from './components/ArticleCard.vue'
  import HomeHero from './components/HomeHero.vue'

  import data from '../data.json' 
</script>
<HomeHero />
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-4349091134125615" crossorigin="anonymous"></script>
<Hero name="Anderson Vilela" subtitle="A Frontend developer (him/her) currently building with vue.js" />
<ArticleCard :data="data" />
