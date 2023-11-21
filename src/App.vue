<template>
  <div class="flex flex-col items-center justify-center w-full h-screen">
    <ScrollList
      :list="list"
      :index="index"
      :visibleItems="5"
    >
      <template #default="{ item }">
        <PersonItem v-bind="item" />
      </template>
    </ScrollList>

    <IndexForm
      v-model="index"
      :max="list.length - 1"
      :min="0"
      @update:modelValue="index = $event"
    />
  </div>
</template>

<script setup>
import { ref } from "vue";
import ScrollList from "./components/ScrollList.vue";
import PersonItem from "./components/PersonItem.vue";
import IndexForm from "./components/IndexForm.vue";
import { list } from "./assets/dataSource";

const index = ref(0)
</script>