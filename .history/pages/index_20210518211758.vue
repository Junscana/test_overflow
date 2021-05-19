<template>
  <main class="home">
    <h1 class="key-visual">
      <img src="~/assets/images/kv/kv-sp-text.jpg" alt="OVERFLOWアーティスト写真" class="sp">
      <img src="~/assets/images/kv/kv-pc-text2.jpg" alt="OVERFLOWアーティスト写真" class="pc">
    </h1>
    <div class="bar" />
    <!-- news -->
    <!-- <section class="top-section news">
      <div class="top-section__header">
        <h2 class="top-section__header__title">news<span class="title-ul"></span></h2>
      </div>
      <div class="top-section__body">
        <ul class="artile">
          <li v-for="content in contents" :key="content.id" class="artile__item">
            <nuxt-link :to="`/${content.id}`" class="artile__item__inner">
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
      <div class="top-section__footer">
        <layout-btn-default url="/news/" text="view more" />
      </div>
    </section> -->
    <!-- /news -->
    <!-- schedule -->
    <section class="top-section schedule">
      <div class="top-section__header">
        <h2 class="top-section__header__title">schedule<span class="title-ul"></span></h2>
      </div>
      <div class="top-section__body">
        <layout-schedule />
        <section class="sns">
          <div class="top-section__header">
            <h3 class="top-section__header__title">sns<span class="title-ul"></span></h3>
          </div>
          <div class="sns__content">
            <section class="sns__content__item twitter">
              <div class="twitter__inner">
                <a class="twitter-timeline" data-height="500" data-theme="light" href="https://twitter.com/ssuggoi_live?ref_src=twsrc%5Etfw">Tweets by ssuggoi_live</a>
                <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
              </div>
              <sns-follow-btn media="twitter" :url="twitter.url" :src="twitter.src" :alt="twitter.alt" />
            </section>
            <section class="sns__content__item">
              <div class="instagram__item instagram">
                <div class="instagram__inner">
                  <img src="http://placehold.jp/300x500.png?text=Instagram" alt="Instagram埋め込み" class="sp">
                  <img src="http://placehold.jp/00x500.png?text=Instagram" alt="Instagram埋め込み" class="pc" style="height: 502px;">
                </div>
                <sns-follow-btn media="instagram" :url="instagram.url" :src="instagram.src" :alt="instagram.alt" />
              </div>
            </section>
          </div>
        </section>
      </div>
    </section>
    <!-- /schedule -->
    <!-- online shop -->
    <section v-if="false" class="top-section online-shop">
      <div class="top-section__header">
        <h2 class="top-section__header__title">online&nbsp;shopへ</h2>
      </div>
      <div class="top-section__body">
        <layout-online-shop />
      </div>
      <div class="top-section__footer">
        <layout-btn-extarnal url="https://www.instagram.com/" text="online shopへ" />
      </div>
    </section>
    <!-- /online shop -->
    <breadcrumb :breadcrumbs="breadcrumbs" />
  </main>
</template>

<script>
export default {
  head: {
    title: 'HOME',
    meta: [
    //   { hid: "og:site_name", property: "og:site_name", content: "OVERFLOWオフィシャルサイト" },
    //   { hid: "og:type", property: "og:type", content: "website" },
    //   { hid: "og:url", property: "og:url", content: "サイトURL" },
    //   { hid: "og:title", property: "og:title", content: "OVERFLOWオフィシャルサイト" },
    //   { hid: "og:description", property: "og:description", content: "OVERFLOWのオフィシャルサイトです。OVERFLOWに関する情報を発信しています。" },
    //   { hid: "og:image", property: "og:image", content: "サイトイメージ" },
      { hid: 'twitter:image', name: 'twitter:image', content: '~@/assets/images/eyecatch/sate-image__default.jpg' }
    //   { name: "twitter:card", content: "summary" },
    //   { hid: "twitter:site", name: "twitter:site", content: "@ssuggoi_live" }
    ]
  },
  data () {
    return {
      twitter: {
        url: 'https://twitter.com/intent/follow?screen_name=ssuggoi_live',
        src: require('~/assets/images/sns/twitter-bird.png'),
        alt: 'Twitterのロゴ'
      },
      instagram: {
        url: 'https://www.instagram.com/',
        src: require('~/assets/images/sns/instagram.png'),
        alt: 'Twitterのロゴ'
      },
      breadcrumbs: [
      ]
    }
  }
  // async asyncData () {
  //   const { data } = await axios.get(
  //     'https://test-overflow.microcms.io/api/v1/news',
  //     {
  //       headers: { 'X-API-KEY': '00d0f46f-ab37-4aae-8779-83154b895434' }
  //     }
  //   )
  //   return data
  // }
}
</script>

<style lang="scss">
main.home {
  padding: 0;
  margin-top: 0;
}

// 帯パーツここから
.bar::before {
  content: '';
  display: block;
  height: 5rem;
  width: 100%;
  background: rgb(255,219,255);
  background: linear-gradient(90deg, rgba(255,219,255,1) 0%, rgba(255,219,255,1) 34%, rgba(255,255,255,1) 100%);
}
// 帯パーツここまで

// snsここから
.sns {
  margin-top: 4rem;
}

.twitter,
.instagram {
  margin-top: 2rem;
}

.twitter__inner {
  border: 1px solid #ccc;
  box-sizing: border-box;
}
// snsここまで

// セクション共通部分
.top-section {
  margin-top: 4rem;
}

.top-section__header__title {
  padding: 0 1.5rem 0.8rem;
  font-size: 2.4rem;
  text-align: center;
  text-transform: uppercase;
  position: relative;
}

.top-section__body {
  margin: 2rem 1.5rem 0;
}

.top-section__footer {
  .btn-area-extarnal {
    margin-top: 2rem;
  }
}
// セクション共通部分ここまで

// scheduleここから
.top-section.schedule {
  margin: 4rem auto 0;
}

.top-section__body .schedule {
  margin: 0;
}
// scheduleここまで

// 共通（ボタン外部リンク）ここから
.btn-area-extarnal__btn-default {
  text-transform: uppercase;
}
// 共通（ボタン外部リンク）ここまで

@media screen and (min-width: 768px) {
  .top-section {
    max-width: 100rem;
    margin: 4rem auto 0;
  }

  .sns__content {
    display: flex;
    justify-content: space-between;
  }

  .sns__content__item {
    width: 44rem;
  }
}
</style>
