<template>
    <section class="bg-blue-50 px-4 py-10">
        <div class="container-xl lg:container m-auto">
            <h2 class="text-3xl font-bold text-green-500 mb-6 text-center">
                Browse Jobs
            </h2>
            <JobsList v-for="job in jobs.slice(0, limit || jobs.lenght)" 
            :key="job.id" 
            :job="job" />
        </div>
    </section>

    <section v-if="showButton" class="m-auto max-w-lg my-10 px-6">
      <RouterLink
        to="/jobs"
        class="block bg-black text-white text-center py-4 px-6 rounded-xl hover:bg-gray-700"
        >View All Jobs</RouterLink
      >
    </section>
</template>

<script setup>
import jobData from '@/jobs.json';
import { ref } from 'vue';
import JobsList from './JobList.vue';
import { RouterLink } from 'vue-router';

const jobs = ref(jobData.jobs)

const props = defineProps({
    limit: Number,
    showButton: Boolean,
});
</script>
