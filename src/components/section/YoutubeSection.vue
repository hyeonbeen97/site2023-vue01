<template>
  <section id="youtubeSection" :class="attr">
    <div class="youtube__inner container">
      <div class="youtube__text">
        <h3>코딩 유튜버 추천</h3>
        <p>
          더 다양한 강의는 유튜브를 통해 제공하고 있습니다. <br />구독과 좋아요!
          부탁드립니다.
        </p>
        <a href="#" class="button-red">자세히 보기</a>
      </div>
      <div class="youtube__item">
        <div>
          <img src="@/assets/images/youtube/youtube01.jpg" alt="유투브" />
        </div>
        <div>
          <img src="@/assets/images/youtube/youtube02.jpg" alt="유투브" />
        </div>
        <div>
          <img src="@/assets/images/youtube/youtube03.jpg" alt="유투브" />
        </div>
        <div>
          <img src="@/assets/images/youtube/youtube04.jpg" alt="유투브" />
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: {
    attr: String,
  },
};
</script>

<style lang="scss">
// youtube__section
.youtube__wrap {
  overflow: hidden;
}
.youtube__inner {
  height: 560px;

  .youtube__text {
    h3 {
      font-size: 50px;
      margin-bottom: 40px;
    }
    p {
      font-size: 22px;
      font-weight: 300;
      margin-bottom: 30px;
    }
    a {
      @include border(50px);
    }
  }
  .youtube__item {
    @include flex-between;
    margin-top: 70px;
    position: absolute;

    > div {
      width: 400px;
      margin-right: 20px;

      img {
        width: 100%;
        @include border(10px);
      }
    }
  }
}

// youtube__page
.youtube__slider {
  display: none;
}
.youtube__search {
  text-align: center;
  margin-bottom: 50px;

  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    @include border(50px);
    min-width: 300px;
    margin-right: 10px;
  }
  button {
    @include button(#f7100d, #fff);
    @include border(50px);
  }
}
.youtube__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;

    li {
      a {
        border: 1px solid #f7100d;
        padding: 10px 20px;
        margin: 0 10px;
        color: #f7100d;
      }
    }
  }
}
.youtube__cont {
  ul {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    margin-bottom: 100px;

    li {
      width: 31.333%;
      margin-bottom: 4%;

      span {
        display: block;
        margin: 4px 0;
      }
    }
  }
}
</style>
