<template>
  <h1 class="blog-title">Blog</h1>
  <div v-for="item in paginatedData" :key="item.id">
    <a :href="item.path" class="container-item">
      <div class="item">
        <h2 class="title">{{ item.Title || 'clique em uma tag' }}</h2>
        <p class="date">{{ item.Updated || "default" }}</p>
      </div>
    </a>
  </div>
  <div class="pagination">
    <span
      v-for="i in totalPages()"
      :key="i"
      @click="switchPage(i)"
      v-bind:class="getBackground(i)"
      >{{ i }}</span>
  </div>
</template>

<script>
import { isString } from '@vue/shared';

export default {
  props: ['data'],
  data: () => ({
    currentPage: 1,
    perPage: 5,
  }),
  computed: {
    paginatedData() {

      if (isString(this.data)) {
        return 1;
      }else {
        const start = (this.currentPage - 1) * this.perPage;
        const end = start + this.perPage;
        return this.data.slice(start, end);
      }
      
    },
  },
  methods: {
    switchPage(index) {
      this.currentPage = index;
    },
    getBackground(property) {
      if (property == this.currentPage) return "selected";
    },
    totalPages() {
      if (isString(this.data)) {
        return 1;
      }else {

        return Math.ceil(this.data.length / this.perPage);
      }
    },
  },
};
</script>

<style scoped>
.blog-title {
  text-align: center;
  font-weight: bold;
  font-size: 2rem;
  margin-top: 24px;
}

.container-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.item {
  padding: 0;
  width: 85%;
  border-radius: 10px;
  padding: 0 20px;
  margin: 10px;
  background: var(--vp-c-bg);
  max-width: 600px;
  box-shadow: 6px 6px #a27b5c;
  border: 4px solid #3f4e4f;
  cursor: pointer;
}

.item:hover {
  text-decoration: none;
  transform: translate(-2px, -2px);
  box-shadow: 10px 10px #a27b5c;
}

.title {
  color: #a27b5c;
  font-size: 1.2em;
  font-weight: bold;
  padding: 0;
  margin: 0;
}

.date {
  padding: 0;
  margin: 0;
  padding-bottom: 7px;
}

.pagination {
  margin-top: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
}

.pagination > span {
  border: 1px solid #534143;
  width: 2rem;
  height: 2rem;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}

.pagination > span:hover {
  width: 2.2rem;
  height: 2.2rem;
}

.selected {
  background: #a27b5c;
}
</style>
