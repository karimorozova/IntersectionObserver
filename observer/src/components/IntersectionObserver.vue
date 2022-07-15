<template lang="pug">
span(ref="observer" )
</template>

<script>
export default {
  name: 'IntersectionObserver',
  props: {
    options: {
      type: Object,
      default: () => ({
        root: null,
        rootMargin: '150px',
        threshold: "0"
      })
    },
  },
  data() {
    return {
      observer: null,
    }
  },
  methods: {
    handleIntersect(entry) {
      if(entry.isIntersecting) this.$emit('triggerIntersected')
    },
  },
  mounted() {
    this.observer = new IntersectionObserver(entries => {
      this.handleIntersect(entries[0])
    }, this.options)
    this.observer.observe(this.$refs.observer)
  },
  unmounted() {
    this.observer.disconnect()
  }
}
</script>

<style lang="scss" scoped>
span {
 display: block;
 width: 10px;
 height: 10px;
 background-color: red;
}
</style>

