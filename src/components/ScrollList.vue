<template>
  <ul
    v-focus
    ref="itemsListRef"
    class="overflow-y-scroll border border-dashed border-zinc-800 w-1/4"
    tabindex="0"
  >
    <li
      v-for="(item, idx) in list"
      :key="`${item.name}${idx}`"
      ref="itemFromListRef"
    >
      <slot :item="item" />
    </li>
  </ul>
</template>

<script setup>
import { onMounted, ref, computed, watch } from 'vue';

const props = defineProps({
  list: {
    type: Array,
    required: true
  },
  index: {
    type: Number,
    default: 0,
  },
  visibleItems: {
    type: Number,
    default: 5
  },
});

const itemsListRef = ref()
const itemFromListRef = ref()
const itemIndex = computed(() => props.index)

function setRootHeight() {
  const item = itemFromListRef.value[0]

  if (item) {
    const itemHeight = item.clientHeight;
    const rootHeight = props.visibleItems * itemHeight;
    itemsListRef.value.style.height = `${rootHeight}px`;
  }
}

function scrollToItem(index) {
  const listContainer = itemsListRef.value;

  const itemElement = listContainer.children[index];
  itemElement.scrollIntoView({ behavior: 'smooth' });
}

watch(itemIndex, scrollToItem)

const vFocus = {
  mounted: (el) => el.focus()
}

defineExpose({scrollToItem})

onMounted(setRootHeight)
</script>