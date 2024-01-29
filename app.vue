<script setup>

// Commented out if the project requires more than one page for router and links
// const navLinks = [
//   { to: "/", label: "Home" },
//   { to: "/about", label: "About" },
// ];

import AppHeader from "@/components/AppHeader.vue";
</script>

<template>
  <AppHeader />
  <main class="p-4">
    <div class="mx-auto container">
      <nav>
        <ul class="flex gap-4">
          <li
            v-for="link in navLinks"
            :key="link.to"
            class="rounded-lg bg-fuchsia-400 p-2 text-white hover:bg-orange"
          >
            <NuxtLink :to="link.to">
              {{ link.label }}
            </NuxtLink>
          </li>
        </ul>
      </nav>
      
      <NuxtPage />
    </div>
  </main>
</template>

<style>

* {
  font-family: 'Inter', sans-serif;
}

h1 {
  font-size: 32px;
}

</style>
