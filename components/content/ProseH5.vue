<template>
  <h5 :id="id" class="scroll-m-20 text-base lg:text-lg font-bold tracking-tight [&:not(:first-child)]:mt-6">
    <NuxtLink
      v-if="id && generate"
      :href="`#${id}`"
    >
      <slot />
    </NuxtLink>
    <slot v-else />
  </h5>
</template>

<script setup lang="ts">
const props = defineProps<{ id?: string }>();

const { headings } = useRuntimeConfig().public.mdc;
const generate = computed(() => props.id && headings?.anchorLinks?.h4);
</script>
