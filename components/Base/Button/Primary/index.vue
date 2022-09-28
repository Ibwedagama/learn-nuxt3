<template>
  <button
    :class="{
      'py-3 px-4 flex gap-4 justify-center items-center text-white rounded-lg': true,
      'bg-green-600 text-white hover:bg-green-500': props.type === 'success',
      'bg-yellow-500 text-gray-800 hover:bg-yellow-400': props.type === 'warning',
      'bg-red-500 text-white hover:bg-red-400': props.type === 'danger',
      'w-full': props.fullWidth,
      'w-fit': !props.fullWidth,
      'mx-auto': props.center
    }
    "
  >
    <slot name="left-icon" />
    <slot />
    <slot name="right-icon" />
  </button>
</template>

<script lang="ts">
export default {
  name: 'BaseButtonPrimary'
}
</script>

<script setup lang="ts">
  interface Props {
    type: string,
    fullWidth?: boolean,
    center?: boolean,
  }

const props = defineProps<Props>()
</script>
