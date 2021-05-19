<template>
  <main class="profile">
    <page-title title="profile" />
    <div class="page-body">
      <layout-member />
    </div>
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
.group {
  padding: 0 1.5rem;
}

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
