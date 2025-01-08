<script setup lang="ts">
import type { Card } from '~/components/Base/Card.vue'

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

const cards: Card[] = [
  {
    title: 'Sales',
    progression: 12,
    amount: 1244.43,
    label: 'View sales',
    description: 'Total sales for the month',
    icon: 'solar:ticket-sale-outline',
  },
  {
    title: 'Refunds',
    progression: 8,
    amount: 84.44,
    label: 'View refunds',
    description: 'Refunds since beginning of the year',
    icon: 'heroicons-outline:receipt-refund',
  },
  {
    title: 'Payouts',
    progression: 14,
    amount: 899.99,
    label: 'View payouts',
    description: 'Payouts of this week',
    icon: 'tabler:zoom-money',
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
      <Tabs default-value="Today" class="w-[400px]">
        <TabsList>
          <TabsTrigger v-for="item in tabsList" :key="item.title" :value="item.title">
            {{ item.title }}
          </TabsTrigger>
        </TabsList>
        <TabsContent v-for="item in tabsList" :key="item.title" :value="item.title">
          <component :is="item.component" />
        </TabsContent>
      </Tabs>
      <!-- <div class="flex items-center gap-4">
        <div v-for="i in 3" :key="i" class="w-[120px] h-[36px] bg-neutral-200 rounded-md" />
      </div> -->
      <section>
        <div class="w-full h-[360px] bg-neutral-200" />
      </section>
    </main>

    <footer>
      <div class="flex justify-between items-center gap-4">
        <BaseCard v-for="item in cards" :key="item.title" :card="item" class="flex-1 w-full h-[240px] bg-neutral-100/20 rounded-md" />
      </div>
    </footer>
  </div>
</template>
