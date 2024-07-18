<template>
  <section class="bg-green-50">
      <div class="container m-auto max-w-2xl py-24">
        <div
          class="bg-white px-6 py-8 mb-4 shadow-md rounded-md border m-4 md:m-0"
        >
          <form @submit.prevent="handleSubmit">
            <h2 class="text-3xl text-center font-semibold mb-6">Add Job</h2>

            <div class="mb-4">
              <label for="type" class="block text-gray-700 font-bold mb-2"
                >Job Type</label
              >
              <select
              v-model="form.type"
                id="type"
                name="type"
                class="border rounded w-full py-2 px-3"
                required
              >
                <option value="Full-Time">Full-Time</option>
                <option value="Part-Time">Part-Time</option>
                <option value="Remote">Remote</option>
                <option value="Internship">Internship</option>
              </select>
            </div>

            <div class="mb-4">
              <label class="block text-gray-700 font-bold mb-2"
                >Job Listing Name</label
              >
              <input
                type="text"
                v-model="form.title"
                id="name"
                name="name"
                class="border rounded w-full py-2 px-3 mb-2"
                placeholder="eg. Beautiful Apartment In Accra"
                required
              />
            </div>
            <div class="mb-4">
              <label
                for="description"
                class="block text-gray-700 font-bold mb-2"
                >Description</label
              >
              <textarea
                id="description"
                v-model="form.description"
                name="description"
                class="border rounded w-full py-2 px-3"
                rows="4"
                placeholder="Add any job duties, expectations, requirements, etc"
              ></textarea>
            </div>

            <div class="mb-4">
              <label for="type" class="block text-gray-700 font-bold mb-2"
                >Salary</label
              >
              <select
               v-model="form.salary"
                id="salary"
                name="salary"
                class="border rounded w-full py-2 px-3"
                required
              >
                <option value="Under GHC 50K">under GHC 50K</option>
                <option value="GHC 50K - GHC 60K">GHC 50 - GHC 60K</option>
                <option value="GHC 60K - GHC 70K">GHC 60 - GHC 70K</option>
                <option value="GHC 70K - GHC 80K">GHC 70 - GHC 80K</option>
                <option value="GHC 80K - GHC 90K">GHC 80 - GHC 90K</option>
                <option value="GHC 90K - GHC 100K">GHC 90 - GHC 100K</option>
                <option value="GHC 100K - GHC 125K">GHC 100 - GHC 125K</option>
                <option value="GHC 125K - GHC 150K">GHC 125 - GHC 150K</option>
                <option value="GHC 150K - GHC 175K">GHC 150 - GHC 175K</option>
                <option value="GHC 175K - GHC 200K">GHC 175 - GHC 200K</option>
                <option value="Over GHC 200K">Over GHC 200K</option>
              </select>
            </div>

            <div class="mb-4">
              <label class="block text-gray-700 font-bold mb-2">
                Location
              </label>
              <input
                type="text"
                v-model="form.location"
                id="location"
                name="location"
                class="border rounded w-full py-2 px-3 mb-2"
                placeholder="Company Location"
                required
              />
            </div>

            <h3 class="text-2xl mb-5">Company Info</h3>

            <div class="mb-4">
              <label for="company" class="block text-gray-700 font-bold mb-2"
                >Company Name</label
              >
              <input
                type="text"
                id="company"
                v-model="form.company.name"
                name="company"
                class="border rounded w-full py-2 px-3"
                placeholder="Company Name"
              />
            </div>

            <div class="mb-4">
              <label
                for="company_description"
                class="block text-gray-700 font-bold mb-2"
                >Company Description</label
              >
              <textarea
                id="company_description"
                v-model="form.company.description"
                name="company_description"
                class="border rounded w-full py-2 px-3"
                rows="4"
                placeholder="What does your company do?"
              ></textarea>
            </div>

            <div class="mb-4">
              <label
                for="contact_email"
                class="block text-gray-700 font-bold mb-2"
                >Contact Email</label
              >
              <input
                type="email"
                id="contact_email"
                v-model="form.company.contactEmail"
                name="contact_email"
                class="border rounded w-full py-2 px-3"
                placeholder="Email address for applicants"
                required
              />
            </div>
            <div class="mb-4">
              <label
                for="contact_phone"
                class="block text-gray-700 font-bold mb-2"
                >Contact Phone</label
              >
              <input
                type="tel"
                id="contact_phone"
                v-model="form.company.contactPhone"
                name="contact_phone"
                class="border rounded w-full py-2 px-3"
                placeholder="Optional phone for applicants"
              />
            </div>

            <div>
              <button
                class="bg-green-500 hover:bg-green-600 text-white font-bold py-2 px-4 rounded-full w-full focus:outline-none focus:shadow-outline"
                type="submit"
              >
                Add Job
              </button>
            </div>
          </form>
        </div>
      </div>
    </section>

</template>

<script setup>
import axios from 'axios';
import { useRouter } from 'vue-router'; 
import { ref } from 'vue';
import { useToast } from 'vue-toastification';

const router = useRouter(); 
const toast = useToast();

const form = ref({
    type: 'Full-Time',
    title: '',
    description: '',
    salary: 'Under GHC 50K',
    location: '',
    company: {
        name: '',
        description: '',
        contactEmail: '',
        contactPhone: ''
    }
});

const handleSubmit = async () => {
    const newJob = {
        type: form.value.type,
        title: form.value.title,
        description: form.value.description,
        salary: form.value.salary,
        location: form.value.location,
        company: {
            name: form.value.company.name, 
            description: form.value.company.description,
            contact_email: form.value.company.contactEmail,
            contact_phone: form.value.company.contactPhone
        }
    };

    try {
        const response = await axios.post(`/api/jobs`, newJob);
        toast.success('Job added successfully');
        router.push(`/jobs/${response.data.id}`);
    } catch (error) {
        console.error('Error posting job', error);
        toast.error('Job could not be added');
    }
};
</script>