<script setup>
const props = defineProps({
  title: { type: String },
  rightText: { type: String },
  rightUrl: { type: String },
  rightName: { type: String },
  showRightChevron: { type: Boolean },
  params: { type: String }
});
</script>

<template>
  <div
    class="theme-bg-color-secondary-static flex justify-between text-white py-[5px] px-[10px] m-p select-none h-[2rem] leading-none items-center">
    <span>
      {{ props.title }}
    </span>

    <span v-if="props.rightText">
      <span v-if="props.rightUrl === undefined">
        {{ props.rightText }}
      </span>
      <NuxtLinkLocale
        v-else
        :to="
          props.params
            ? { name: props.rightUrl, params: props.params }
            : props.rightUrl
        ">
        {{ props.rightText }}
      </NuxtLinkLocale>
      <!-- 右箭头 -->
      <!-- <v-icon v-if="showRightChevron" name="bi-chevron-double-right" /> -->
    </span>
  </div>
</template>

<style scoped></style>
