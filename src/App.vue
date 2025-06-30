<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
<div class="flex flex-col min-h-screen w-full bg-slate-100 dark:bg-slate-900">
  <!-- Header -->
  <header class="bg-slate-700 dark:bg-slate-950">
    <nav class="flex items-center justify-between p-4 w-full">
      <RouterLink class="text-slate-200" to="/">Home</RouterLink>
      <RouterLink class="text-slate-200" to="/dashboard">Dashboard</RouterLink>
      <div class="flex space-x-2">
        <RouterLink class="text-slate-200" to="/login">Login</RouterLink>
        <RouterLink class="text-slate-200" to="/register">Register</RouterLink>
      </div>
    </nav>
  </header>

  <!-- Main content (Shaashada oo dhan) -->
  <main class="flex-1 w-full p-4">
    <RouterView />
  </main>
</div>

</template>
