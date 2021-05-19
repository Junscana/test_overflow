<template>
  <div class="schedule">
    <iframe
      src="https://calendar.google.com/calendar/embed?src=a204c4bmp6k8rl2iu7m6hgucp8%40group.calendar.google.com&ctz=Asia%2FTokyo?wmode=transparent"
      style="border: 0"
      class="sp"
      width="100%"
      height="500"
      frameborder="0"
      scrolling="no"
    />
    <iframe
      src="https://calendar.google.com/calendar/embed?src=a204c4bmp6k8rl2iu7m6hgucp8%40group.calendar.google.com&ctz=Asia%2FTokyo?wmode=transparent"
      style="border: 0"
      class="pc"
      width="100%"
      height="600"
      frameborder="0"
      scrolling="no"
    />
  </div>
</template>

<script>
export default {
  name: 'LayoutSchedule'
}
</script>

<style lang="scss">
.schedule {
  margin: 0 1.5rem;
}

iframe {
  position: relative;
  z-index: 0;
}
</style>
