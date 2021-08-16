<template>
  <div ref="boostCard" v-click-outside="hide" :class="$style.mold">
    <div :class="$style.handle" @click="toggleShow()">
      <span class="icon-plus" />
    </div>
    <div :class="$style.review">
      <div :class="$style.inner">
        <div :class="$style['boost-mold']">
          <div>
            <span>BOOST</span>
          </div>
        </div>
        <div :class="$style.footer">
          <span :class="$style.liking">LIKING</span>
          <span :class="$style.hundred">100</span>
        </div>
      </div>
    </div>
    <div :class="$style.popup">
      <div :class="$style.title">
        CREATE BOOST
      </div>
      <div :class="$style['date-header']">
        <div :class="$style.dashed" />
        <div :class="$style.caption">
          Date Period
        </div>
        <div :class="$style.dashed" />
      </div>
      <div :class="$style['date-body']">
        <div>Pick Date Range:</div>
        <div :class="$style.to">
          TO
        </div>
        <div :class="$style.date">
          <div>2020/09/10</div>
          <div>2020/09/10</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import vClickOutside from 'v-click-outside'

export default {
  name: 'BoostCard',
  directives: {
    clickOutside: vClickOutside.directive
  },
  methods: {
    toggleShow (operation = undefined) {
      const classList = this.$refs.boostCard.classList
      const className = this.$style.selected
      if (operation === 'hide') {
        classList.remove(className)
      } else {
        classList.contains(className) ? classList.remove(className) : classList.add(className)
      }
    },
    hide () {
      this.toggleShow('hide')
    }
  }
}
</script>

<style lang="scss" module>
@import "boost-card";
</style>
