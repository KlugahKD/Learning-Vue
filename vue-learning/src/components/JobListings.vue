<template>
    <JobLoaders v-if="loading" />
    <section v-else class="bg-blue-50 px-4 py-10">
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
import { ref, onMounted } from 'vue';
import JobsList from './JobList.vue';
import { RouterLink } from 'vue-router';
import  axios from 'axios';
import JobLoaders from '@/loaders/JobLoaders.vue';

const jobs = ref([]);
const loading = ref();

const props = defineProps({
    limit: Number,
    showButton: Boolean,
});

onMounted(async () => {
    try{
        loading.value = true;
    const response = await axios.get('http://localhost:8000/jobs');
    jobs.value = response.data;
    } catch (error) {
        console.error("Error fetching jobs", error);
    }

    finally {
        loading.value = false;
    }
});
</script>
