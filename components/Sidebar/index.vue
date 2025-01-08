<script setup>
const isOpen = ref(false)

function toggleIsOpen() {
  isOpen.value = !isOpen.value
}
</script>

<template>
  <div class="relative">
    <div class="flex lg:hidden justify-between items-center w-full h-full p-4 z-50">
      <Logo />
      <Icon
        name="iconamoon:menu-burger-horizontal"
        :size="30"
        class="left-2 top-2 cursor-pointer z-50"
        @click="toggleIsOpen"
      />
      <div v-if="isOpen" class="fixed top-0 left-0 w-full h-screen bg-white z-[999]">
        <Icon
          name="material-symbols:close"
          :size="30"
          class="absolute right-4 top-4 cursor-pointer z-50"
          @click="toggleIsOpen"
        />
        <SidebarMenu />
      </div>
    </div>
    <div class="hidden lg:flex flex-col justify-between w-[250px] h-screen border-r border-gray-200 z-50">
      <SidebarMenu />
      <div>
        UserItem
      </div>
    </div>
  </div>
</template>
