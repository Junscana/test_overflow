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
    <!-- <breadcrumb :breadcrumbs="breadcrumbs" /> -->
  </main>
</template>

<script>
export default {}
</script>

<style lang="scss">
</style>
