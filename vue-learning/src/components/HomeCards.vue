<template>
  <section class="py-4">
      <div class="container-xl lg:container m-auto">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-4 rounded-lg">
            <Card title="For Developers" 
            description="Browse our Dan jobs and start your career today"
            buttonDescription="Browse Jobs" 
            link="jobs.html" 
            bgColor="bg-gray-100" 
            buttonColor="bg-black"
            hoverColor="hover:bg-gray-700"/>


            <Card title="For Employers"
            description="Post a job and find the best candidates for your company"
            buttonDescription="Post a Job"
            link="add-job.html"
            bgColor="bg-green-100"
            buttonColor="bg-green-500"
            hoverColor="hover:bg-green-600"/>
        </div>
      </div>
    </section>
</template>

<script setup>
import Card from '@/components/Card.vue';

</script>
