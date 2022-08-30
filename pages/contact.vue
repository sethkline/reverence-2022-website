<template>
  <form @submit.prevent="submitForm" class="space-y-8 divide-y divide-gray-200 p-4">
    <div class="space-y-8 divide-y divide-gray-200">
      <div>
        <div>
          <h1 class="text-lg leading-6 font-medium text-gray-900">Contact Us</h1>
          <p class="mt-1 text-sm text-gray-500">This information will be displayed publicly so be careful what you share.</p>
        </div>

        <div class="mt-6 grid grid-cols-1 gap-y-6 gap-x-4 sm:grid-cols-6">
          <div class="sm:col-span-6">
            <label for="name" class="block text-sm font-medium text-gray-700"> Name</label>
            <div class="mt-1">
              <input v-model="form.name" type="text" name="name" id="name" autocomplete="name" required class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md" />
            </div>
          </div>
          <div class="sm:col-span-6">
            <label for="first-name" class="block text-sm font-medium text-gray-700"> Email</label>
            <div class="mt-1">
              <input v-model="form.email" type="email" name="email" id="email" autocomplete="email" required class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border-gray-300 rounded-md" />
            </div>
          </div>

          <div class="sm:col-span-6">
            <label for="about" class="block text-sm font-medium text-gray-700"> Message: </label>
            <div class="mt-1">
              <textarea v-model="form.message" id="about" name="message" rows="3" class="shadow-sm focus:ring-indigo-500 focus:border-indigo-500 block w-full sm:text-sm border border-gray-300 rounded-md" required />
            </div>
            <p class="mt-2 text-sm text-gray-500">Write a few sentences about yourself.</p>
          </div>
        </div>
      </div>
    </div>

    <div class="pt-5">
      <div class="flex justify-start">
        <button type="submit" class="ml-3 inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">Send</button>
      </div>
    </div>
  </form>
</template>
<script setup lang="ts">
import axios from 'axios';

interface Form {
  name: string;
  email: string;
  message: string;
}

const form = reactive<Form>({
  name: null,
  email: null,
  message: null
})



const submitForm = () => {
 let submission = JSON.stringify(form)
 axios.post('https://b5nbdwvqp5.execute-api.us-east-1.amazonaws.com/dev/static-site-mailer', submission).then((response) => console.log(response))
}

</script>