<template>
  <section class="member">
    <h2 class="member__title fontUppercase">member</h2>
    <ul class="member__list">
      <li v-for="(memberItem, index) in memberList" :key="index" class="member__list__item" :class="memberItem.id">
        <nuxt-link :to="memberItem.url">
          <dl class="member__list__item__inner">
            <dd class="member__list__item__inner__img">
              <img :src="memberItem.src" :alt="memberItem.alt">
            </dd>
            <dt class="member__list__item__inner__name">{{ memberItem.name }}</dt>
          </dl>
        </nuxt-link>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'LayoutMember',
  data () {
    return {
      memberList: [
        {
          name: 'メンバー１',
          src: require('~/assets/images/member/member1_square.jpg'),
          alt: 'メンバー１のアー写',
          url: '/profile/member/member1/',
          id: 'member1'
        },
        {
          name: 'メンバー２',
          src: require('~/assets/images/member/member2_square.jpg'),
          alt: 'メンバー２のアー写',
          url: '/profile/member/member2/',
          id: 'member2'
        },
        {
          name: 'メンバー３',
          src: require('~/assets/images/member/member3_square.jpg'),
          alt: 'メンバー３のアー写',
          url: '/profile/member/member3/',
          id: 'member3'
        },
        {
          name: 'メンバー４',
          src: require('~/assets/images/member/member4_square.jpg'),
          alt: 'メンバー４のアー写',
          url: '/profile/member/member4/',
          id: 'member4'
        },
        {
          name: 'メンバー５',
          src: require('~/assets/images/member/member5_square.jpg'),
          alt: 'メンバー５のアー写',
          url: '/profile/member/member5/',
          id: 'member5'
        },
        {
          name: 'メンバー６',
          src: require('~/assets/images/member/member6_square.jpg'),
          alt: 'メンバー６のアー写',
          url: '/profile/member/member6/',
          id: 'member6'
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
          name: 'メンバー１',
          path: ''
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.member {
  margin-top: 4rem;
  padding: 0 1.5rem;

  &__title {
    font-size: 2rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid #333;
    box-sizing: border-box;
    font-weight: bold;
  }
}

.member__list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  margin-top: 4rem;

  &__item {
    width: 48%;
    margin-top: 2rem;

    &__inner {
      position: relative;
    }

    &__inner__name {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 40%;
      width: 100%;
      background-color: rgba(255, 255, 255, 0.4);
      text-align: center;
      box-sizing: border-box;
      position: absolute;
      right: 0;
      bottom: 0;
    }

    &:first-of-type, &:nth-of-type(2) {
      margin-top: 0;
    }
  }
}

@media screen and (min-width: 768px) {
  .member {
    padding: 0;
  }

  .member__list {
    justify-content: flex-start;

    &__item {
      width: 32%;
      margin-left: 2%;

      &__inner__name {
        height: 30%;
        font-size: 1.8rem;
      }

      &:first-of-type,
      &:nth-of-type(4) {
        margin-left: 0;
      }

      &:nth-of-type(3) {
        margin-top: 0;
      }
    }
  }
}
</style>
