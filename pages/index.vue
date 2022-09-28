<template>
  <BaseContainer>
    <main class="w-full bg-gray-300 p-10">
      <h1 class="text-center">
        {{ title }}
      </h1>
      <br>
      <section class="flex gap-5 justify-center">
        <BaseButton
          variant="primary"
          type="success"
          @click="changeTitle"
        >
          <template #left-icon>
            <span>👉</span>
          </template>
          Change Title
        </BaseButton>

        <BaseButton
          variant="secondary"
          type="danger"
          @click="resetTitle"
        >
          <template #left-icon>
            <span>👉</span>
          </template>
          Reset Title
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
