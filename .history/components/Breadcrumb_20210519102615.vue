<template>
  <div class="l-breadcrumb">
    <div class="l-breadcrumb__inner">
      <ul class="l-breadcrumb__inner__items">
        <li class="l-breadcrumb__inner__items__item" v-for="breadcrumb in breadcrumbs" :key="breadcrumb.name">
          <nuxt-link
            v-if="breadcrumb.path"
            :to="breadcrumb.path"
            class="l-breadcrumb__inner__items__item__text--link fontUppercase"
          >
            <span>{{ breadcrumb.name }}</span>
          </nuxt-link>
          <span v-else class="l-breadcrumb__inner__items__item__text--nolink fontUppercase">{{ breadcrumb.name }}</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Breadcrumb',
  props: {
    breadcrumbs: Array
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="scss">
.l-breadcrumb{
  margin-top: 6rem;
  background: rgb(255,245,255);
  background: linear-gradient(90deg, rgba(255,245,255,1) 0%, rgba(237,242,255,1) 100%);

  &__inner {
    display: flex;
    align-items: center;
    height: 6rem;
    margin: 0 1.5rem;
    // overflow-x: scroll;
    // word-break: keep-all;
    // white-space: nowrap;
    // -webkit-overflow-scrolling: touch;

    &__items {
      display: flex;
      flex-wrap: wrap;
    }

    &__items__item::before {
      content: '＞';
      margin: 0 1rem;
    }

    &__items__item:first-of-type::before {
      display: none;
    }

    &__items__item__text--link {
      color: #1a0dab;
    }
  }
}

@media screen and (min-width: 768px) {
  .l-breadcrumb{
    &__inner {
      max-width: 100rem;
      margin: 6rem 1.5rem 0;
    }
  }
}
</style>
