<script setup>
const navLinks = [
  { to: "/", label: "Home" },
  { to: "/about", label: "About" },
];

import AppHeader from "@/components/AppHeader.vue";
</script>

<template>
  <AppHeader />
  <div class="p-2">
    <header>
      <nav>
        <ul class="flex gap-4">
          <li
            v-for="link in navLinks"
            :key="link.to"
            class="rounded-lg bg-green-500 p-2 text-white hover:text-orange-300"
          >
            <NuxtLink :to="link.to">{{ link.label }}</NuxtLink>
          </li>
        </ul>
      </nav>
    </header>
    <NuxtPage />
  </div>
</template>

<style>
h1 {
  font-size: 32px;
}
</style>
