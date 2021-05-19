<template>
  <main class="member2">
    <page-title title="profile" />
    <div class="page-body">
      <div class="page-member">
        <div class="page-member__img">
          <img :src="src" :alt="alt">
        </div>
        <section class="page-member__content">
          <div class="page-member__content__name">
            <h2 class="page-member__content__name--ja">{{ nameJa }}</h2>
            <p class="page-member__content__name--en">{{ nameEn }}</p>
          </div>
          <ul class="page-member__content__info">
            <li class="page-member__content__info__item">
              <ul class="page-member__content__info__item__sns-list">
                <li v-for="(snsItem, index) in snsList" :key="index" class="page-member__content__info__item__sns-list__item">
                  <a :href="snsItem.url" class="page-member__content__info__item__sns-list__inner">
                    <img :src="snsItem.src" :alt="snsItem.alt">
                  </a>
                </li>
              </ul>
            </li>
            <li v-for="(infoItem, index) in infoList" :key="index" class="page-member__content__info__item">
              <dl class="page-member__content__info__item__inner">
                <dt class="page-member__content__info__item__inner__title">{{ infoItem.title }}</dt>
                <dd class="page-member__content__info__item__inner__content">{{ infoItem.content }}</dd>
              </dl>
            </li>
          </ul>
        </section>
      </div>
      <layout-member />
    </div>
    <layout-btn-default url="/profile/" text="メンバー一覧に戻る" />
    <breadcrumb :breadcrumbs="breadcrumbs" />
  </main>
</template>

<script>
export default {
  head: {
    title: 'MEMBER',
    meta: [
      {
        hid: 'keyword',
        name: 'keyword',
        content: 'メンバー名, 趣味, 特技,'
      },
      {
        hid: 'description',
        name: 'description',
        content: 'メンバー名に関する情報をお届けしてます。'
      }
    ]
  },
  data () {
    return {
      el: '#app',
      id: 'member2',
      src: require('~/assets/images/member/member2_square.jpg'),
      alt: 'member2のアー写',
      nameJa: 'メンバー２',
      nameEn: 'member',
      infoList: [
        {
          title: '誕生日',
          content: 'テキストテキストテキスト'
        },
        {
          title: '星座',
          content: 'テキストテキスト'
        },
        {
          title: '出身',
          content: 'テキストテキストテキスト'
        },
        {
          title: '趣味',
          content: 'テキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキストテキスト'
        },
        {
          title: '特技',
          content: 'テキストテキストテキストテキストテキストテキストテキストテキストテキスト'
        }
      ],
      snsList: [
        {
          url: 'https://twitter.com/',
          src: require('~/assets/images/sns/twitter.png'),
          alt: 'twitterのロゴ'
        },
        {
          url: 'https://www.instagram.com/',
          src: require('~/assets/images/sns/instagram.png'),
          alt: 'Instagramのロゴ'
        },
        {
          url: 'https://www.youtube.com/',
          src: require('~/assets/images/sns/showroom.png'),
          alt: 'SHOWROOMのロゴ'
        }
      ],
      breadcrumbs: [
        {
          name: 'home',
          path: '/'
        },
        {
          name: 'profile',
          path: '/profile/'
        },
        {
          name: 'メンバー２',
          path: ''
        }
      ]
    }
  },
  mounted () {
    const targetElement = this.$el
    const targetMember = targetElement.getElementsByClassName(this.id)
    targetMember[0].remove()
  }
}
</script>

<style lang="scss" scoped>
.page-body {
  margin-top: 4rem;
}

.page-member__img {
  padding: 0 1.5rem;
}

.page-member__content {
  margin-top: 4rem;
  padding: 01.5rem;

  &__name {
    &--ja {
      font-size: 2.4rem;
      font-weight: bold;
    }

    &--en {
      margin-top: 0.6rem;
    }
  }
}

.page-member__content__info {
  display: flex;
  flex-wrap: wrap;
  margin-top: 2rem;

  &__item {
    width: 100%;
    margin-top: 1rem;

    &:nth-of-type(2) {
      margin-top: 2rem;
    }

    &:first-of-type {
      margin-top: 0rem;
    }
  }

  &__item__inner {
    display: flex;

    &__title {
      width: 8rem;
    }

    &__title::after {
      content: '：';
    }

    &__content {
      width: calc(100% - 8rem);
    }
  }
}

.page-member__content__info__item__sns-list {
  display: flex;
  align-items: center;

  &__item {
    width: 4rem;
    margin-left: 2rem;

    &:first-of-type {
      margin-left: 0;
    }
  }
}

.member6 {
  #member6 {
    display: none;
  }
}

@media screen and (min-width: 768px) {
  .page-member {
    display: flex;

    &__img {
      width: 43%;
      padding: 0;
    }

    &__content {
      width: 55%;
      margin-top: 0;
      margin-left: 2%;
      padding: 0;
    }
  }

  .page-member__content__info {
    display: flex;
    flex-wrap: wrap;
    margin-top: 2rem;

    &__item {
      width: 100%;
      margin-top: 1rem;

      &:nth-of-type(2) {
        margin-top: 2rem;
      }
    }
  }

  .member__list {
    justify-content: flex-start;
  }
}
</style>
