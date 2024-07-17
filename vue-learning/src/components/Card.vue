<template>
   <div class="p-6 rounded-lg shadow-md" :class="bgColor">
            <h2 class="text-2xl font-bold">
                {{ title }}
            </h2>
            <p class="mt-2 mb-4">
              {{ description}}
            </p>
            <a
              href="link"
              class="inline-block text-white rounded-lg px-4 py-2" :class="[hoverColor, buttonColor]">
              {{ buttonDescription }}
            </a>
          </div>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    required: true,
},
  description: {
    type: String,
    required: true,
  },
  buttonDescription: {
    type: String,
    required: true,
  },
    bgColor: {
        type: String,
        required: true,
    },
  link: {
    String,
    required: true,
  },
  hoverColor: {
    type: String,
    required: true,
  },
  buttonColor: {
    type: String,
    required: true,
  },
});

</script>