<script setup lang="ts">
export interface Card {
  title: string
  progression: number
  amount: number
  label: string
  description?: string
  icon?: string
}

defineProps<{
  card: Card
}>()
</script>

<template>
  <Card :title="card.title" class="px-4 pt-4 pb-2">
    <CardHeader class="flex-row justify-between items-center">
      <p>{{ card.title }}</p>
      <Badge :value="`${card.progression}%`" class="bg-green-400">
        {{ `${card.progression}%` }}
      </Badge>
    </CardHeader>
    <CardContent class="flex justify-end items-center px-4 pt-0 pb-2 border-b">
      <div class="text-[48px] font-[800]">
        <span class="text-neutral-300">$</span>
        <span class="text-neutral-800">{{ card.amount }}</span>
      </div>
    </CardContent>
    <CardFooter class="flex justify-between items-center gap-2 px-2 py-2">
      <div class="flex justify-center items-center w-8 h-8 bg-neutral-200 rounded-md">
        <Icon :name="card.icon" size="20" color="black " />
      </div>
      <p class="grow max-w-[120px] text-xs truncate">
        {{ card.description }}
      </p>
      <Button variant="outline">
        {{ card.label }}
      </Button>
    </CardFooter>
  </card>
</template>
