<script setup lang="js">
const highBrightnessControllerStore = useHighBrightnessControllerStore();
const router = useRouter();

router.afterEach((to, from) => {
  highBrightnessControllerStore.obj[to.path] =
    !highBrightnessControllerStore.obj[to.path];
});

const { $mitt } = useNuxtApp();
const bodyRef = useTemplateRef('mainBody');

</script>

<template>
  <NuxtLayout>
    <div ref="mainBody" class="flex-1 pl-[1px]">
      <!-- <NuxtPage /> -->
    </div>
  </NuxtLayout>
</template>
