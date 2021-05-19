<template>
  <main class="profile">
    <section class="page-contents">
      <page-title title="about" />
      <div class="page-body">
        <section class="group">
          <div class="group__image">
            <!-- <img src="http://placehold.jp/300x200.png?text=KV" alt="OVERFLOWアーティスト写真"> -->
            <img src="~/assets/images/kv/kv-pc.jpg" alt="OVERFLOWアーティスト写真">
          </div>
          <div class="group__desc">
            <h2 class="group__desc__title fontUppercase">overflow</h2>
            <div class="group__desc__content">
              <p>ダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキスト
                <br /><br />ダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキストダミーテキスト
              </p>
            </div>
          </div>
        </section>
        <!-- <layout-member /> -->
      </div>
    </section>
    <breadcrumb :breadcrumbs="breadcrumbs" />
  </main>
</template>

<script>
export default {
  head: {
    title: 'PROFILE',
    meta: [
      {
        hid: 'keyword',
        name: 'keyword',
        content: 'キーワード１, キーワード２, キーワード３'
      },
      {
        hid: 'description',
        name: 'description',
        content: 'OVERFLOWのグループ説明です。'
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
          name: 'profile',
          path: ''
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
.group__desc {
  margin-top: 4rem;

  &__title {
    font-size: 2rem;
    font-weight: bold;
  }

  &__content {
    margin-top: 2rem;
  }
}
</style>
