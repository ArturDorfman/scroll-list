<template>
  <form
    class="w-1/4 mt-10 flex items-center justify-center"
    @submit.prevent="$emit('update:modelValue', index)"
  >
    <label class="mr-3 text-lg font-medium text-slate-900">Scroll to: </label>
    <input
      type="number"
      v-model="index"
      name="index"
      class="p-2 border border-dashed rounded-md border-slate-900 w-36"
      placeholder="Enter index"
      :min="min"
      :max="max"
    />
    <button
      type="submit"
      class="p-2 ml-3 text-white rounded-md bg-slate-900"
    >
      Enter
    </button>
  </form>
</template>

<script setup>
import { ref } from "vue";

const props = defineProps({
  modelValue: {
    type: Number,
    default: 0,
  },
  max: {
    type: Number,
    required: true,
  },
  min: {
    type: Number,
    default: 0,
  },
});

defineEmits(["update: modelValue"]);

const index = ref(0)
</script>
