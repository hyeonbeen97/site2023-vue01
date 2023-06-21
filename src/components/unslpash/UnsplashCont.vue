<template>
  <div className="unsplash__cont container">
    <ul>
      <li v-for="(unsplash, index) in unsplashs" :key="index">
        <a :href="`https://unsplash.com/photos/${unsplash.id}`">
          <img :src="unsplash.urls.regular" :alt="unsplash.alt_description" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    unsplashs: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
// unsplash__wrap
.unsplash__wrap {
}
.unsplash__inner {
  height: 600px;
  h3 {
    font-size: 50px;
    margin-bottom: 20px;
  }
  p {
    margin-bottom: 30px;
    font-size: 22px;
  }
  a {
    @include button(#ecaa52, #e7f1ee);
    border-radius: 30px;
  }
  .unsplash__item {
    position: absolute;
    margin-top: 70px;
    display: flex;
    justify-content: space-between;
    > div {
      width: 400px;
      margin-right: 20px;

      img {
        width: 100%;
      }
    }
  }
}
</style>
