<script setup>
const emit = defineEmits(['onClickRemove']);

defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number,
});
</script>

<template>
  <div class="flex items-center border border-slate-200 p-4 rounded-xl gap-4">
    <img class="w-16 h-16" :src="imageUrl" :alt="title" />
    <div class="flex flex-col w-full">
      <p>{{ title }}</p>
      <div class="flex justify-between items-end mt-2 gap-2">
        <b>{{ price }} UAH</b>
        <img
          @click="emit('onClickRemove')"
          class="opacity-40 hover:opacity-100 cursor-pointer transition ml-auto"
          src="/close.svg"
          alt="Close"
        />
      </div>
    </div>
  </div>
</template>
