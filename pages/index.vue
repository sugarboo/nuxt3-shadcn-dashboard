<script setup>
</script>

<template>
  <div class="grid gap-8">
    <header class="flex justify-between items-start">
      <div class="grow">
        <p>Ground control to major Tom</p>
        <h1>Dashboard</h1>
      </div>
      <div class="w-[120px] h-[36px] bg-neutral-200 rounded-md" />
    </header>

    <main class="grid gap-2">
      <div class="flex items-center gap-3">
        <div v-for="i in 3" :key="i" class="w-[120px] h-[36px] bg-neutral-200 rounded-md" />
      </div>
      <section>
        <div class="w-full h-[360px] bg-neutral-200" />
      </section>
    </main>

    <footer>
      <div class="flex justify-between items-center gap-3">
        <div v-for="i in 3" :key="i" class="flex-1 w-full h-[240px] bg-neutral-200 rounded-md" />
      </div>
    </footer>
  </div>
</template>
