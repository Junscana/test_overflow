<template>
  <main>
    <section>
      <page-title title="schedule" />
      <div class="page-body">
        <layout-schedule />
      </div>
    </section>
    <breadcrumb :breadcrumbs="breadcrumbs" />
  </main>
</template>

<script>
import LayoutSchedule from '~/components/LayoutSchedule.vue'
export default {
  components: { LayoutSchedule },
  head: {
    title: 'SCHEDULE',
    meta: [
      {
        hid: 'keyword',
        name: 'keyword',
        content: 'OVERFLOW, スケジュール, イベント,'
      },
      {
        hid: 'description',
        name: 'description',
        content: 'OVERFLOWのスケジュールを掲載してます。'
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
          name: 'schedule',
          path: ''
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
