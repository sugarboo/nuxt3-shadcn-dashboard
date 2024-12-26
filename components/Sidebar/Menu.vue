<script setup>
const items = ref([
  {
    title: 'Overview',
    path: '/overview',
    icon: 'ri:dashboard-line',
  },
  {
    title: 'Transactions',
    path: '/transactions',
    icon: 'ri:exchange-dollar-line',
  },
  {
    title: 'Account',
    path: '/account',
    icon: 'ri:user-line',
  },
  {
    title: 'Contacts',
    path: '/contacts',
    icon: 'ri:contacts-line',
  },
  {
    title: 'Settings',
    path: '/settings',
    icon: 'ri:settings-line',
  },
])
</script>

<template>
  <div>
    <header class="flex items-center gap-2 p-4 hover:scale-[101%] transition-all duration-300 cursor-pointer">
      <Logo />
      <p class="font-bold">
        Nuxt Finance
      </p>
    </header>
    <div class="px-4 grow">
      <div class="">
        <ul class="grid gap-4">
          <li v-for="{ path, title, icon } in items" :key="path">
            <NuxtLink :to="path" class="flex items-center gap-2 p-2 rounded-md hover:bg-gray-100 transition-all duration-300">
              <Icon :name="icon" :size="20" color="black" />
              <p class="font-semibold">
                {{ title }}
              </p>
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
