<template>
  <div class="ContainerTags">
    <h2>Tags</h2>
    <div class="tags">
      <span 
        v-for="tag in tags"
        @click="tagsFiltered(tag)"
      >{{ tag }}</span>
    </div>
    <div>
     <ArticleCard :data="filtered" /> 
    </div>
  </div>
</template>
<script>
import data from '../../data.json';
import ArticleCard from "./ArticleCard.vue";

export default {
  components: {
    ArticleCard,
  },
  data: () => ({
    data: data,
    tags: [
      "react",
      "css",
      "javascript",
      "typescript",
      "vue.js"
    ],
    filtered: 'clique em uma tag',
  }),
  methods: {
    tagsFiltered(tag) {
      const filtered = this.data.filter((element) => {
        return element.tag == tag
      })

     this.filtered = filtered;
    }
  }
}

</script>

<style>
.ContainerTags > h2 {
  font-size: 2rem;
  font-weight: 500;
  border: none;
  
}

.ContainerTags > .tags {
  display: flex;
  gap: 1rem;

  border-bottom: 1px dashed #C7C7C7;
  padding: 1rem;
}

.ContainerTags > .tags span {
  cursor: pointer;
}
  
</style>
