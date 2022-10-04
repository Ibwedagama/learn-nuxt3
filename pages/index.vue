<template>
  <BaseContainer>
    <main class="w-full p-10">
      <h1 class="text-center">
        {{ title }}
      </h1>
      <br>
      <section class="flex gap-5">
        <BaseButton
          variant="primary"
          type="success"
          :full-width="false"
          :center="false"
          @click="changeTitle"
        >
          Change Title
        </BaseButton>
      </section>
    </main>
  </BaseContainer>
</template>

<script>
</script>

<script setup lang="ts">
import type { Ref } from 'vue'

const title: Ref<string> = ref('Hello World')

const changeTitle = () => {
  title.value = 'New Title'
}

const resetTitle = () => {
  title.value = 'Hello World'
}
</script>
