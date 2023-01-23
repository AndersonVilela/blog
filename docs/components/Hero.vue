<template>
  <div class="shareCard">
    <h1 class="title">
      <span>Hi, I'm {{ name || "Anderson Vilela" }}</span>
    </h1>
    <p class="description">
      {{ subtitle }}
    </p>
  </div>
</template>

<script>
import { inject } from '@vercel/analytics';

inject();
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    subtitle: {
      type: String,
      required: true,
    },
  },
};
</script>
<style scoped>
.shareCard {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 0 15px;
  text-align: center;
}
.title {
  display: flex;
  align-items: center;
  font-size: 2.2em;
  font-weight: bold;
}
.description {
  margin: 1em 0;
}
</style>

<style>
body {
  display: grid;
  place-items: center;
}
</style>
