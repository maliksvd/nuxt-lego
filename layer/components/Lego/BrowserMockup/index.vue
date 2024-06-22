<script lang="ts" setup>
defineProps<{
  url: {
    type: String;
    required: true;
  };
  colored: {
    type: Boolean;
    default: false;
  };
}>(); // Add a semicolon at the end
</script>
<template>
  <div
    class="w-full h-full rounded-2xl border rounded-lg overflow-hidden flex flex-col"
  >
    <div class="flex space-x-8 h-12 bg-white flex items-center px-4 border-b">
      <div class="flex gap-2 w-20">
        <div
          class="w-3 h-3 rounded-full bg-gray-200/40 border hover:bg-red-400 transition-colors duration-200 ease-in-out cursor-pointer"
          :class="{ 'bg-red-400': colored }"
        ></div>
        <div
          class="w-3 h-3 rounded-full bg-gray-200/40 border hover:bg-yellow-400 transition-colors duration-200 ease-in-out cursor-pointer"
          :class="{ 'bg-yellow-400': colored }"
        ></div>
        <div
          class="w-3 h-3 rounded-full bg-gray-200/40 border hover:bg-green-400 transition-colors duration-200 ease-in-out cursor-pointer"
          :class="{ 'bg-green-400': colored }"
        ></div>
      </div>
      <div class="flex-1" v-if="url">
        <div
          class="w-60 border bg-gray-200/40 rounded-md px-2 py-1 hover:bg-white transition-colors duration-200 ease-in-out cursor-pointer"
        >
          <div class="flex items-center">
            <p
              class="text-xs text-center text-nowrap text-gray-400 font-light overflow-hidden"
            >
              {{ url }}
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="flex-1 p-5 bg-white">
      <slot />
    </div>
  </div>
</template>
