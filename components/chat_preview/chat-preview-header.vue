<script setup lang="ts">
import Popper from "vue3-popper";

const { openedChat } = storeToRefs(useGeneralStore());

const { onClickFilter } = defineProps<{
  onClickFilter: any;
}>();
</script>

<template>
  <div
    class="md:!flex flex justify-between w-full py-3 pl-4 pr-2 border-b duration-300"
    :class="{ 'hidden': openedChat?.conversations.length !== 0 }"
  >
    <Popper arrow offset-distance="top-end">
      <div class="flex items-center gap-1 cursor-pointer h-9">
        <div class="font-semibold text-sm">Open</div>
        <div class="font-semibold text-[13px] text-slate-400">8</div>
        <Icon name="octicon:chevron-down-24" size="20" class="bg-slate-700" />
      </div>
      <template #content>
        <div class="border p-1 rounded bg-white text-[12px] mt-1">Display</div>
      </template>
    </Popper>
    <div class="flex items-center gap-1 duration-300">
      <div
        class="rounded-full hover:bg-slate-100 px-2 flex items-center justify-center duration-200 cursor-pointer"
        @click="onClickFilter()"
      >
        <Icon name="bi:sort-up-alt" size="22" class="bg-blue-500" />
      </div>
    </div>
  </div>
</template>
