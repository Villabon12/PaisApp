<script setup lang="ts">
import { defineProps } from "vue";
import { Country } from "../models/country.model";

interface Props {
  country: Country;
}

defineProps<Props>();
</script>

<template>
  <div class="max-w-sm bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
    <img class="rounded-t-lg object-cover h-56 sm:h-36 w-full" :src="country.flags.png" :alt="country.flags.alt" />
  </div>
  <div class="p-5">
    <h4 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">{{ country.name.common }}</h4>
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">
      Capital:
      <span v-for="capital in country.capital" class="font-bold">{{
        capital
        }}
        <template> </template>
      </span>
    </p>
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">
      Population:
      <span class="font-bold">{{ country.population?.toLocaleString() }}</span>
    </p>
    <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">
      Region:
      <span class="font-bold">{{ country.region }}</span>
    </p>
  </div>
</template>
