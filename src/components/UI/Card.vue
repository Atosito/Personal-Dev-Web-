<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    imgUrl: {
      type: String,
    },
    link: {
      type: String,
    },
  },
};
</script>


<template>
     <div class="card">
    <div v-if="imgUrl" class="card-img__wrapper">
      <img class="card-img" :src="imgUrl" :alt="title" />
    </div>
    <span class="card-name">{{ name }}</span>
    <span class="card-title">{{ title }}</span>
    <div class="card-body">
      <slot name="body"></slot>

      <router-link
        v-if="link"
        class="link"
        style="display: block; margin-top: 16px"
        :to="link"
        >See more</router-link
      >
    </div>
    <slot name="footer"></slot>
  </div>
</template>

<style scoped>
.card {
  width: 300px;
  display: inline-block;
  margin: auto;
  border-radius: 14px + 5;
  position: relative;
  text-align: center;
  box-shadow: -1px 15px 30px -12px rgba(50, 50, 50, 0.2);
}
.card-img__wrapper {
  position: relative;
  height: 230px;
  border-top-left-radius: 14px;
  border-top-right-radius: 14px;
}

.card-img {
  width: 400px;
}

.card-name {
  display: block;
  margin-top: 24px;
  margin-bottom: 6px;
  text-transform: uppercase;
  font-size: 12px;
  font-weight: 700;
}

.card-title {
  display: block;
  margin-bottom: 8px;
  font-size: 26px;
  color: black;
  font-weight: 900;
}

.card-body {
  padding: 20px;
  margin-bottom: 16px;
}
</style>