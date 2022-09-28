<template>
  <component
    :is="buttonVariant"
    :type="props.type"
    :full-width="props.fullWidth"
    :center="props.center"
  >
    <template #left-icon>
      <slot name="left-icon" />
    </template>
    <template #default>
      <slot />
    </template>
    <template #right-icon>
      <slot name="right-icon" />
    </template>
  </component>
</template>

<script lang="ts">
export default {
  name: 'BaseButton'
}
</script>

<script setup lang="ts">
  interface Props {
    type: string,
    variant?: string,
    fullWidth?: boolean,
    center?: boolean,
  }

const props = withDefaults(defineProps<Props>(), {
  type: 'success',
  variant: 'primary',
  fullWidth: false,
  center: false
})

const buttonVariant = computed(() => {
  switch (props.variant) {
    case 'secondary':
      return resolveComponent('BaseButtonSecondary')

    case 'tertiary':
      return resolveComponent('BaseButtonTertiary')

    default:
      return resolveComponent('BaseButtonPrimary')
  }
})
</script>
