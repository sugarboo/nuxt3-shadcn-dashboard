<script setup>
const tabsList = [
  {
    title: 'Today',
    component: resolveComponent('TabsToday'),
  },
  {
    title: 'Week',
    component: resolveComponent('TabsWeek'),
  },
  {
    title: 'Month',
    component: resolveComponent('TabsMonth'),
  },
  {
    title: 'Year',
    component: resolveComponent('TabsYear'),
  },
]
</script>

<template>
  <div class="grid gap-4 w-full">
    <header class="flex justify-between items-start">
      <div class="grow">
        <p>Ground control to major Tom</p>
        <h1>Dashboard</h1>
      </div>
      <div class="w-[120px] h-[36px] bg-neutral-200 rounded-md" />
    </header>

    <main class="grid gap-4">
      <Tabs default-value="today" class="w-[400px]">
        <TabsList>
          <TabsTrigger v-for="item in tabsList" :key="item.component" :value="item.title">
            {{ item.title }}
          </TabsTrigger>
        </TabsList>
        <TabsContent v-for="item in tabsList" :key="item.component" :value="item.title">
          <component :is="item.component" />
        </TabsContent>
      </Tabs>
      <div class="flex items-center gap-4">
        <div v-for="i in 3" :key="i" class="w-[120px] h-[36px] bg-neutral-200 rounded-md" />
      </div>
      <section>
        <div class="w-full h-[360px] bg-neutral-200" />
      </section>
    </main>

    <footer>
      <div class="flex justify-between items-center gap-4">
        <div v-for="i in 3" :key="i" class="flex-1 w-full h-[240px] bg-neutral-200 rounded-md" />
      </div>
    </footer>
  </div>
</template>
