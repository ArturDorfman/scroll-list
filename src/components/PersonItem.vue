<template>
  <div class="flex items-center gap-4 p-4">
    <img :src="avatar" class="w-12 h-12 rounded-full" />
    <p class="flex flex-col">
      <strong class="text-sm font-medium text-slate-900">
        {{ name }}
      </strong>
      <span class="text-sm font-medium text-slate-500">
        {{ profession }}
      </span>
    </p>
  </div>
</template>

<script setup>
defineProps({
  avatar: {
    type: String,
    required: true,
  },
  name: {
    type: String,
    required: true
  },
  profession: {
    type: String,
    required: true,
  },
});
</script>