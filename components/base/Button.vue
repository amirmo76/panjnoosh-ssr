<template>
  <button
    :class="{
      button: true, 
      contained: type === 'contained', 
      outlined: type === 'outlined',
      text: type === 'text',
      lg: size === 'lg', 
      md: size === 'md', 
      sm: size === 'sm', 
      stretched: size === 'stretched',
      primary: color === 'primary',
      white: color === 'white',
      round: round,
      disabled: disabled,
      pressed: pressed,
      flat: flat
      }"
    :disabled="disabled"
    v-ripple
  >
    <span class="icon">
      <slot name="icon"></slot>
    </span>
    <span class="label" v-if="$slots.default">
      <slot></slot>
    </span>
  </button>
</template>

<script>
export default {
  name: "Button",
  data() {
    return {
      pressed: false
    }
  },
  props: {
    type: {
      type: String
    },
    disabled: {
      type: Boolean,
      default: false
    },
    color: {
      type: String,
      default: 'primary'
    },
    size: {
      type: String,
      default: "md"
    },
    flat: {
      type: Boolean,
      default: false
    },
    round: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style lang="stylus" scoped>
@import '~assets/styles/variables';

.button 
  border none
  font-family inherit
  font-size $font-size
  outline none
  position relative
  z-index 1
  transition all .3s
  display flex
  flex-direction row-reverse
  align-items center
  .icon
    margin-left 1rem
    display flex
    align-items center
    fill $black
  .icon:last-of-type
    margin-left 0
  &:hover
    cursor: pointer

.contained 
  border-radius: 4px
  box-shadow: 
    0px 3px 3px -2px rgba(0, 0, 0, 0.2), 
    0px 2px 5px 0px rgba(0, 0, 0, 0.14), 
    0px 1px 5px 0px rgba(0,0,0,.12)
  &:hover
    box-shadow:
      0px 4px 7px -2px rgba(0, 0, 0, 0.2), 
      0px 3px 9px 0px rgba(0, 0, 0, 0.14), 
      0px 2px 10px 0px rgba(0,0,0,.12)

  &.sm 
    padding: 1rem 2.5rem
  &.md 
    padding: 1rem 5rem
  &.lg 
    padding: 1rem 10rem
  &.stretched 
    width: 100%

  &.flat
    box-shadow none
    &:hover
      box-shadow none

  &.primary 
    background-color $primary
    color $black
  &.white
    background-color $white
    color $black

  &.disabled
    background-color #CCCCCC
    box-shadow none
    color #909090

  &:focus::after 
    width 100%
    height 100%
    display block
    content ""
    position absolute 
    top 0
    left 0
    z-index 2
    background-color rgba(white, .2)

.text
  border-radius: 4px  
  background-color transparent
  transition none
  color $black 
  &:hover
  &:focus
    background-color rgba(#CCCCCC, .25)
  &.sm 
    padding: 1rem 2.5rem
  &.md 
    padding: 1rem 5rem
  &.lg 
    padding: 1rem 10rem
  &.stretched 
    width: 100%

  &.primary
    color $primary
    .icon
      fill $primary
    &:hover
    &:focus
      background-color rgba($primary, .25)
  &.white
    color $white
    .icon
      fill $white
    &:hover
    &:focus
      background-color rgba($white, .05)
        
  &.round
    border-radius 50%
    &.sm
      padding 1.2rem
    &.md 
      padding: 2rem
    &.lg 
      padding: 4rem
  

  

</style>

