<template>
  <div class="bg-gray-50">
    <div class="max-w-7xl mx-auto py-12 px-4 sm:py-16 sm:px-6 lg:px-8">
      <div class="max-w-3xl mx-auto divide-y-2 divide-gray-200">
        <dl class="mt-6 space-y-6 divide-y divide-gray-200">
          <Disclosure
            as="div"
            v-for="danceClass in classes"
            :key="danceClass.name"
            class="pt-6"
            v-slot="{ open }"
          >
            <dt class="text-lg">
              <DisclosureButton
                class="text-left w-full flex justify-between items-start text-gray-400"
              >
              <div class="flex space-x-2">
                    <PlusIcon v-if="!open" class="h-6 w-6" aria-hidden="true" />
                    <MinusIcon v-else class="h-6 w-6 transform -rotate-6" aria-hidden="true" />
                <span class="text-2xl font-medium text-gray-900">
                  {{ danceClass.name }}
                </span>
              </div>
              </DisclosureButton>
            </dt>
            <transition
              enter-active-class="transition duration-100 ease-out"
              enter-from-class="transform scale-95 opacity-0"
              enter-to-class="transform scale-100 opacity-100"
              leave-active-class="transition duration-75 ease-out"
              leave-from-class="transform scale-100 opacity-100"
              leave-to-class="transform scale-95 opacity-0"
            >
              <DisclosurePanel as="dd" class="mt-2 pr-12">
                <div class="grid space-x-2">
                    <p class="font-medium text-gray-900">Class Time:</p>
                    <p class="text-base text-gray-500">
                      {{ danceClass.time }}
                    </p>
                </div>
                <div v-if="danceClass?.details" class="grid space-x-2">
                    <p class="font-medium text-gray-900">Details:</p>
                    <p class="text-base text-gray-500">
                      {{ danceClass.details }}
                    </p>
                </div>
                <div class="grid space-x-2">
                    <p class="font-medium text-gray-900">Tuition:</p>
                    <p class="text-base text-gray-500">
                      {{ danceClass.tuitionMonthly }}
                    </p>
                </div>
                <div class="grid space-x-2">
                    <p class="font-medium text-gray-900">Dress Code:</p>
                    <p class="text-base text-gray-500">
                      {{ danceClass.dressCode }}
                    </p>
                </div>
              </DisclosurePanel>
            </transition>
          </Disclosure>
        </dl>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Disclosure, DisclosureButton, DisclosurePanel } from "@headlessui/vue";
import { ChevronDownIcon, PlusIcon, MinusIcon } from "@heroicons/vue/outline";

interface DressCode {
  leotard?: string;
  tights?: string;
  shoes?: string;
}

interface Class {
  name: string;
  time: string;
  tuitionMonthly: number;
  details: string;
  recital: "AM" | "PM";
  dressCode: DressCode;
}

const classes: Class[] = [
  {
    name: "Ballet 1A",
    time:
      "I don't know, but the flag is a big plus. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas cupiditate laboriosam fugiat.",
    tuitionMonthly: 50,
    details: "This is a good class",
    recital: "AM",
    dressCode: {
      leotard: "with attached skirt",
      tights: "Ballet Pink",
      shoes: "Pink Ballet",
    },
  },
  // More questions...
];
</script>
