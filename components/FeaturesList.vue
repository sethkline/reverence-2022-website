<!-- This example requires Tailwind CSS v2.0+ -->
<template>
  <div class="bg-rev-red-700">
    <div class="max-w-4xl mx-auto px-4 py-16 sm:px-6 sm:pt-20 sm:pb-24 lg:max-w-7xl lg:pt-24 lg:px-8">
      <h2 class="text-3xl font-extrabold text-white tracking-tight">Our dance philosophy is simple:</h2>
      <h3 class="text-2xl font-extrabold text-white tracking-tight">High-quality dance education in a Christ-centered environment.</h3>
      <p class="mt-4 max-w-3xl text-lg text-rev-red-200">Our music is clean. Our costumes are modest. Our teachers are life-giving and ready to invest in each student individually. Our business is focused on investing in our dancers and reaching out to the community. Our classroom environment is inclusive of all students from all ages, walks of life, faith backgrounds, and special needs. Our students are THE BEST in the world.</p>
      <div class="mt-12 grid grid-cols-1 gap-x-6 gap-y-12 sm:grid-cols-2 lg:mt-16 lg:grid-cols-4 lg:gap-x-8 lg:gap-y-16">
        <div v-for="feature in features" :key="feature.name">
          <div>
            <span class="flex items-center justify-center h-12 w-12 rounded-md bg-white bg-opacity-10">
              <component :is="feature.icon" class="h-6 w-6 text-white" aria-hidden="true" />
            </span>
          </div>
          <div class="mt-6">
            <h3 class="text-lg font-medium text-white">{{ feature.name }}</h3>
            <p class="mt-2 text-base text-rev-red-200">
              {{ feature.description }}
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import {
  ChatAltIcon,
  DocumentReportIcon,
  HeartIcon,
  InboxIcon,
  PencilAltIcon,
  ReplyIcon,
  TrashIcon,
  UsersIcon,
  ShieldCheckIcon,
  UserCircleIcon,
  AcademicCapIcon,
  GlobeIcon,
} from '@heroicons/vue/outline'

const features = [
  {
    name: 'A Safe Haven for Learning:',
    description: 'We are pleased to provide a safe place for your child to learn dance that is free from pressure, superstars, competition, and offensive themes and undertones. We ensure that all of our themes and ideas contain positive, life-affirming messages.',
    icon: ShieldCheckIcon,
  },
  {
    name: 'A Well-Rounded Dance Education:',
    description: 'Our staff are well-trained in a variety of different dance styles and are great examples for students to look up to. We bring in special guest artists to teach workshops for our students, and we have relationships with local and national dance companies like Encountered Heart Dance Company and Paradosi Ballet Company that are extremely beneficial to our students. Students ages 11 & up have the opportunity to apply for our Student Leadership Program to assist in classes for younger students.',
    icon: AcademicCapIcon,
  },
  {
    name: 'Community Outreach',
    description: 'We believe that the art of dance is a gift meant to be shared with others. Over the past 14 years, we have had teams of students perform at local festivals, libraries, nursing homes, retirement communities, churches, schools, and more! These performances are wonderful learning opportunities for our students, but also meaningful to our community. Many of our staff have also taught dance classes at churches, for local refugee communities, and at children and youth centers as part of our community outreach goals. We are also proud to be an inclusive studio that permits students with special needs to take regular weekly dance classes.',
    icon: UsersIcon,
  },
  {
    name: 'Impacting the Nations',
    description: 'Révérence Studios dancers and staff have traveled nationally and throughout the world to spread the message of God’s love through dance to the nations prior to the Pandemic. These past two years we have helped other studios put on their virtual recitals and shared our curriculum with Christian dance studios just starting up in other countries. Through our original Bible ballets, students have been able to raise thousands of dollars to benefit missions work throughout the world.',
    icon: GlobeIcon,
  },
]
</script>