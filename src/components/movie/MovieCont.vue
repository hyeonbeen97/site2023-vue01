<template>
  <div class="movie__cont container">
    <ul>
      <li v-for="(movie, index) in movies" :key="index">
        <a
          :href="`https://www.themoviedb.org/movie/${movie.id}`"
          target="_blank"
        >
          <img
            :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`"
            :alt="movie.title"
          />
        </a>
        <em>
          <span class="title">{{ movie.title }}</span>
          <span class="star">{{ movie.vote_average }}</span>
        </em>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
// movies__wrap
.movies__wrap {
}
.movies__inner {
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
    @include button(#007c0a, #e7f1ee);
    border-radius: 30px;
  }
  .movies__item {
    position: absolute;
    margin-top: 70px;

    > div {
      width: 300px;
      margin-right: 20px;

      img {
        width: 100%;
        height: 200%;
        border-radius: 30px;
        object-fit: cover;
      }
    }
  }
}
// moviepage
#moviePage {
  .cont__title {
    h2 {
      color: #49a85e;
    }
  }
}
.movie__slider {
  display: block;
  width: 100%;
  height: 1000px;
}
.movie__search {
  text-align: center;
  margin-bottom: 50px;
  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    min-width: 300px;
    margin-right: 10px;
    @include border(50px);
  }
  button {
    @include button(#bb0000, #e7f1ee);
    @include border(50px);
  }
}
.movie__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-bottom: 50px;

    li {
      a {
        border: 1px solid #b6ccee;
        padding: 10px 20px;
        margin: 10px;
        color: #b6ccee;
        span {
          display: block;
          margin: 4px 0;
        }
      }
    }
  }
}
.movie__cont {
  ul {
    columns: 4;
    column-gap: 20px;

    li {
      margin-bottom: 4%;
      position: relative;

      .title {
        font-size: 20px;
      }
      .star {
        position: absolute;
        right: 20px;
        top: 20px;
        width: 30px;
        height: 30px;
        background-color: #fff;
        font-size: 12px;
        text-align: center;
        line-height: 30px;
        border-radius: 50%;
        color: #000;
      }

      img {
        width: 100%;
        transition: all 0.3s;
        border-radius: 5px;

        &:hover {
          transform: scale(110%);
          cursor: pointer;
        }
      }
    }
  }
}
</style>
