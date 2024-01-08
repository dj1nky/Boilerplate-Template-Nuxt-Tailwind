<script setup>
const { data } = await useFetch("https://restcountries.com/v3.1/all");

const sortArray = computed(() => {
  // Create a shallow copy of the original data to avoid modifying it directly
  const sortedArray = [...data.value];
  sortedArray.sort((a, b) => {
    return a.name.common.localeCompare(b.name.common);
  });
  return sortedArray;
});
</script>

<template>
  <div class="mt-2 p-2">
    <div class="flex flex-col gap-2 sm:grid md:grid-cols-3 lg:grid-cols-4">
      <div
        v-for="(countries, index) in sortArray"
        :key="index"
        class="rounded-lg border-2"
      >
        <div class="flex flex-col gap-2 p-4 lg:w-64">
          <div
            v-for="(capital, innerIndex) in countries.capital"
            :key="innerIndex"
          >
            <p class="font-bold">
              {{ countries.name.common }}
            </p>
            <p>{{ capital }}</p>
            <p>Population: {{ countries.population }}</p>
          </div>
          <nuxt-img :src="countries.flags.png" />
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
