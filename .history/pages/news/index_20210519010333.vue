<template>
  <main class="news">
    <section class="page-contents">
      <page-title title="news" />
      <div class="page-body">
        <ul class="article">
          <li v-for="content in contents" :key="content.id" class="artile__item">
            <nuxt-link :to="'/news/' + content.id + '/'" class="artile__item__inner">
            <div class="artile__item__inner__header">
              <sapn v-text="$dayjs(content.published).locale('ja').format('YYYY/MM/DD')"  class="artile__item__inner__header__date" />
              <span v-if="content.category == 'event'" class="artile__item__inner__header__category event fontUppercase">event</span>
              <span v-if="content.category == 'news'" class="artile__item__inner__header__category news fontUppercase">news</span>
              <span v-if="content.category == 'media'" class="artile__item__inner__header__category media fontUppercase">media</span>
            </div>
            <div class="artile__item__inner__body">
              <p class="artile__item__inner__body__title">{{ content.title }}</p>
            </div>
            </nuxt-link>
          </li>
        </ul>
      </div>
    </section>
    <breadcrumb :breadcrumbs="breadcrumbs" />
  </main>
</template>

<script>
import axios from 'axios'
export default {
  async asyncData ({ $config }) {
    const { data } = await axios.get(`${$config.apiUrl}/news`, {
      headers: { 'X-API-KEY': $config.apiKey }
    })
    return {
      contents: data.contents
    }
  },
  head: {
    title: 'NEWS',
    meta: [
      {
        hid: 'keyword',
        name: 'keyword',
        content: 'ニュース, イベント, ライブ, メディア'
      },
      {
        hid: 'description',
        name: 'description',
        content: 'OVERFLOWのニュースはこちらのページでお届けしています'
      }
    ]
  },
  data () {
    return {
      breadcrumbs: [
        {
          name: 'home',
          path: '/'
        },
        {
          name: 'news',
          path: ''
        }
      ]
    }
  }
}
</script>

<style lang="scss">

.artile__item {
  border-bottom: 1px solid #333;
  position: relative;

  &::after {
    content: "";
    display: block;
    height: 4rem;
    width: 2rem;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    background-image: url('~@/assets/images/icon/icon_arrow-right.png');
    background-size: 160%;
    background-repeat: no-repeat;
    background-position: 50% 40%;
  }

  &:first-of-type {
    border-top: 1px solid #333;
  }
}

.artile__item__inner {
  display: block;
  padding: 2rem 2rem 2rem 0rem;
}

.artile__item__inner__header {
  &__date {
    color: #fa89b9;
  }

  &__category {
    margin-left: 1rem;
    padding: 0.4rem 1rem;
    font-size: 1.4rem;
    box-sizing: border-box;
    border: 1px solid #707070;
    box-sizing: border-box;

    &.event {
      border-color: #ffc241;
    }

    &.news {
      border-color: #ffb1fa
    }

    &.media {
      border-color: #62a8ff;
    }
  }
}

.artile__item__inner__body {
  margin-top: 0.6rem;

  &__title {
    font-size: 1.8rem;
    line-height: 1.4;
  }
}

.article-content__header {
  padding: 0 0 1rem;
  margin: 0 1.5rem;

  &__date {
    color: #fa89b9;
  }
}

@media screen and (min-width: 768px) {
  .page-body {
    max-width: 100rem;
    margin: 2rem auto 0;
  }

  .article-content__header > dt {
    width: 100%;
  }
}
</style>
