<template>
  <button
    :class="{
      'py-3 px-4 flex gap-4 justify-center items-center text-white rounded-lg bg-transparent': true,
      'text-green-600 hover:bg-green-200': props.type === 'success',
      'text-yellow-500 hover:bg-yellow-200': props.type === 'warning',
      'text-red-500 hover:bg-red-200': props.type === 'danger',
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
  name: 'BaseButtonTertiary'
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
