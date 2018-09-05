<template>
  <button class="g-button" :class="{['iconPosition']:true}">
    <svg v-if="icon" class="icon">
      <use :xlink:href="`#i-${icon}`"></use>
    </svg>
    <slot></slot>
  </button>
</template>
<script>
export default {
  props:['icon','iconPosition']
}
</script>
<style lang="scss">
.g-button {
  font-size: var(--font-size);
  height: var(--button-height);
  padding: 0 1em;
  border-radius: var(--border-radius);
  border: 1px solid var(--border-color);
  background: var(--button-bg);
  display: inline-flex;
  justify-content: center;
  align-items: center;
  &:hover{
  border-color: var(--border-color-hover)
}
  &:active{
    border-color: var(--border-active-bg)
  }
  &:focus {
    outline: none;
  }
  &.icon-right{
    > .icon{
      order: 2
    }
  }
}
</style>
